---
title: Migrar da classe XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9404d758-679f-4ffb-995d-3d07d817659e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d8b8c21af8ca0a21d97e8246ad82c42aaaf4974
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272443"
---
# <a name="migrating-from-the-xsltransform-class"></a>Migrar da classe XslTransform
A arquitetura XSLT foi reprojetada na versão [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]. A classe de <xref:System.Xml.Xsl.XslTransform> foi substituída pela classe de <xref:System.Xml.Xsl.XslCompiledTransform> .  
  
 As seções a seguir descrevem algumas das principais diferenças entre <xref:System.Xml.Xsl.XslCompiledTransform> e as classes de <xref:System.Xml.Xsl.XslTransform> .  
  
## <a name="performance"></a>Desempenho  
 A classe de <xref:System.Xml.Xsl.XslCompiledTransform> inclui muitos aprimoramentos de desempenho. O novo processador XSLT compila a folha de estilos XSLT para baixo em um formato intermediário comuns, semelhante ao que o Common Language Runtime (CLR) faz para outras linguagens de programação. Uma vez que a folha de estilos é compilada, pode ser armazenada em cachê e reutilizado.  
  
 A classe de <xref:System.Xml.Xsl.XslCompiledTransform> também inclui outras otimizações que o torna muito mais rápido que a classe de <xref:System.Xml.Xsl.XslTransform> .  
  
> [!NOTE]
>  Embora o desempenho geral da classe <xref:System.Xml.Xsl.XslCompiledTransform> seja melhor do que o da classe <xref:System.Xml.Xsl.XslTransform>, o método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> da classe <xref:System.Xml.Xsl.XslCompiledTransform> possivelmente apresentará um desempenho mais lento do que o método <xref:System.Xml.Xsl.XslTransform.Load%2A> da classe <xref:System.Xml.Xsl.XslTransform> na primeira vez que for chamado em uma transformação. Isso ocorre porque o arquivo XSLT deve ser compilado antes que seja carregado. Para saber mais, confira a postagem de blog a seguir: [XslCompiledTransform mais lento do que XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)  
  
## <a name="security"></a>Segurança  
 Por padrão, o suporte desativa da classe de <xref:System.Xml.Xsl.XslCompiledTransform> para a função XSLT `document()` e script inserido. Esses recursos podem ser ativados criando um objeto de <xref:System.Xml.Xsl.XsltSettings> que possui os recursos ativados e que passa para o método de <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> . O exemplo a seguir mostra como habilitar scripts e executar uma transformação XSLT.  
  
 [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
 [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
 Para saber mais, confira [Considerações sobre segurança relacionadas à reflexão](../../../../docs/standard/data/xml/xslt-security-considerations.md).  
  
## <a name="new-features"></a>Novos recursos  
  
### <a name="temporary-files"></a>Arquivos temporários  
 Os arquivos temporários são gerados às vezes durante processamento XSLT. Se uma folha de estilos contém blocos de script, ou se é criada com a configuração de depuração definida para retificar, os arquivos temporários podem ser criados na pasta % temp %. Pode haver instâncias quando alguns arquivos temporários não são excluídos devido a problemas de tempo. Por exemplo, se os arquivos estão em uso por Appdomain atual ou o depurador, o finalizer do objeto de <xref:System.CodeDom.Compiler.TempFileCollection> não poderá removê-los.  
  
 A propriedade de <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> pode ser usada para que a limpeza adicional certifique-se de que todos os arquivos temporários são removidos de cliente.  
  
### <a name="support-for-the-xsloutput-element-and-xmlwriter"></a>Suporte para o XSL: elemento e XmlWriter de saída  
 A classe de <xref:System.Xml.Xsl.XslTransform> ignorada configurações de `xsl:output` quando a saída transformação foram enviados a um objeto de <xref:System.Xml.XmlWriter> . A classe de <xref:System.Xml.Xsl.XslCompiledTransform> tem uma propriedade de <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A> que retorna um objeto de <xref:System.Xml.XmlWriterSettings> que contém informações de saída derivada de elemento de `xsl:output` folha de estilos. O objeto de <xref:System.Xml.XmlWriterSettings> é usado para criar um objeto de <xref:System.Xml.XmlWriter> com as configurações corretas que podem ser passada para o método de <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> . O código a seguir em c ilustra esse comportamento:  
  
```  
// Create the XslTransform object and load the style sheet.  
XslCompiledTransform xslt = new XslCompiledTransform();  
xslt.Load(stylesheet);  
  
// Load the file to transform.  
XPathDocument doc = new XPathDocument(filename);  
  
// Create the writer.  
XmlWriter writer = XmlWriter.Create(Console.Out, xslt.OutputSettings);  
  
// Transform the file and send the output to the console.  
xslt.Transform(doc, writer);  
writer.Close();  
```  
  
### <a name="debug-option"></a>Opção de depuração  
 A classe de <xref:System.Xml.Xsl.XslCompiledTransform> pode gerar informações de depuração, que permite você depurar a folha de estilos com o Depurador do Microsoft Visual Studio. Consulte <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29> para obter mais informações.  
  
## <a name="behavioral-differences"></a>Diferenças de comportamento  
  
### <a name="transforming-to-an-xmlreader"></a>Uma transformação a um XmlReader  
 A classe de <xref:System.Xml.Xsl.XslTransform> tiver vários transformar as sobrecargas que a transformação de retorno resultados como um objeto de <xref:System.Xml.XmlReader> . Essas sobrecargas podem ser usadas para carregar os resultados de transformação em uma representação em memória (como <xref:System.Xml.XmlDocument> ou <xref:System.Xml.XPath.XPathDocument>) sem incorrer a sobrecarga de serialização e desserialização de árvore XML resultante. O código a seguir em c mostra como carregar os resultados de transformação em um objeto de <xref:System.Xml.XmlDocument> .  
  
```  
// Load the style sheet  
XslTransform xslt = new XslTransform();  
xslt.Load("MyStylesheet.xsl");  
  
// Transform input document to XmlDocument for additional processing  
XmlDocument doc = new XmlDocument();  
doc.Load(xslt.Transform(input, (XsltArgumentList)null));  
```  
  
 A classe de <xref:System.Xml.Xsl.XslCompiledTransform> não oferece suporte a <xref:System.Xml.XmlReader> transformar um objeto. No entanto, você pode fazer algo semelhante usando o método <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A> para carregar a árvore resultante XML diretamente de <xref:System.Xml.XmlWriter>. O código a seguir em c mostra como realizar a mesma tarefa usando <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
```  
// Transform input document to XmlDocument for additional processing  
XmlDocument doc = new XmlDocument();  
using (XmlWriter writer = doc.CreateNavigator().AppendChild()) {  
    xslt.Transform(input, (XsltArgumentList)null, writer);  
}  
```  
  
### <a name="discretionary-behavior"></a>Comportamento arbitrário  
 A recomendação de versão 1,0 do W3C de transformações XSL (XSLT) inclui as áreas no qual o provedor de implementação pode decidir como manipular uma situação. Essas áreas são consideradas como comportamento arbitrário. Há várias áreas onde <xref:System.Xml.Xsl.XslCompiledTransform> se comporta de forma diferente do que a classe de <xref:System.Xml.Xsl.XslTransform> . Para saber mais, confira [Erros recuperáveis de XSLT](../../../../docs/standard/data/xml/recoverable-xslt-errors.md).  
  
### <a name="extension-objects-and-script-functions"></a>Objetos de extensão e funções de script  
 <xref:System.Xml.Xsl.XslCompiledTransform> apresenta duas novas restrições sobre o uso de funções de script:  
  
-   Somente os métodos públicos podem ser chamados de expressões XPath.  
  
-   Sobrecargas são distinguíveis de se com base no número de argumentos. Se mais de uma sobrecarga tem o mesmo número de argumentos, uma exceção será lançada.  
  
 Em <xref:System.Xml.Xsl.XslCompiledTransform>, uma associação (pesquisa do nome do método) funções de script ocorre em tempo de compilação, e as folhas de estilos que trabalharam com XslTranform podem causar uma exceção quando são carregadas com <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 suporte de<xref:System.Xml.Xsl.XslCompiledTransform> que têm `msxsl:using` e elementos filho de `msxsl:assembly` dentro do elemento de `msxsl:script` . Os elementos de `msxsl:using` e de `msxsl:assembly` são usados para declarar namespaces e assemblies adicionais para uso no bloco de script. Para saber mais, confira [Blocos de script usando msxsl:script](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md).  
  
 <xref:System.Xml.Xsl.XslCompiledTransform> proíbe os objetos de extensão que têm várias sobrecargas com o mesmo número de argumentos.  
  
### <a name="msxml-functions"></a>Funções de MSXML  
 Suporte para funções adicionais de MSXML foi adicionado à classe de <xref:System.Xml.Xsl.XslCompiledTransform> . A lista a seguir descreve a funcionalidades novas ou aprimorada:  
  
-   msxsl:node-set: <xref:System.Xml.Xsl.XslTransform> exigiu que o argumento de função de [node-set Function](https://msdn.microsoft.com/library/87b6b3f4-16f4-4fa3-8103-d62a679ac2a7) fosse um fragmento da árvore de resultado. A classe de <xref:System.Xml.Xsl.XslCompiledTransform> não tiver esse requisito.  
  
-   msxsl: versão: Essa função é suportado em <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
-   Funções de extensão XPath: as funções [ms:string-compare Function](https://msdn.microsoft.com/library/20616b82-9e27-444c-b714-4f1e09b73aee), [ms:utc](https://msdn.microsoft.com/library/ef26fc88-84c6-4fb9-9c3b-f2f5264b864f), [ms:namespace-uri](https://msdn.microsoft.com/library/91f9cabf-ab93-4dbe-9c12-e6a75214f4c7), [ms:local-name](https://msdn.microsoft.com/library/10ed60a1-17a9-4d74-8b98-7940ac97c0b5), [ms:number](https://msdn.microsoft.com/library/b94fc08e-1f31-4f48-b1a8-6d78c1b5d954), [ms:format-date](https://msdn.microsoft.com/library/51f35609-89a9-4098-a166-88bf01300bf5) e [ms:format-time](https://msdn.microsoft.com/library/e5c2df2d-e8fb-4a8f-bfc0-db84ea12a5d5) já têm suporte.  
  
-   Funções de extensão Esquema- relacionados XPath: Essas funções não são suportadas nativamente por <xref:System.Xml.Xsl.XslCompiledTransform>. No entanto, podem ser implementados como funções de extensão.  
  
## <a name="see-also"></a>Consulte também

- [Transformações XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)  
- [Usando a classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
