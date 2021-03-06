---
title: Avalia as expressões XPath usando XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2913ccf3-f932-4363-8028-9e2d22ce6093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2712c1de4a5f4a06ba041fdc0c5df2487eebdd2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205407"
---
# <a name="evaluate-xpath-expressions-using-xpathnavigator"></a>Avalia as expressões XPath usando XPathNavigator
A classe de <xref:System.Xml.XPath.XPathNavigator> fornece o método de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> para avaliar uma expressão XPath. O método de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> usa uma expressão XPath, avalia-a e retorna um tipo XPath W3C de booleano, de número, de cadeia de caracteres, ou de conjunto do nó com base no resultado da expressão XPath.  
  
## <a name="the-evaluate-method"></a>O método de avaliação  
 O método de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> usa uma expressão XPath, avalia-a, e retorna um resultado de tipo booleano (<xref:System.Boolean>), o número (<xref:System.Double>), a cadeia de caracteres (<xref:System.String>), ou do conjunto de nó (<xref:System.Xml.XPath.XPathNodeIterator>). Por exemplo, o método de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> pode ser usado em um método matemático. O código exemplo a seguir calcula o custo total de todos os livros no arquivo de `books.xml` .  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Dim query As XPathExpression = navigator.Compile("sum(//price/text())")  
Dim total As Double = CType(navigator.Evaluate(query), Double)  
Console.WriteLine(total)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
XPathExpression query = navigator.Compile("sum(//price/text())");  
Double total = (Double)navigator.Evaluate(query);  
Console.WriteLine(total);  
```  
  
 O exemplo usa o arquivo `books.xml` como entrada.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="position-and-last-functions"></a>funções de posição e o último  
 O método de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> está sobrecarregado. Um dos métodos de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> utiliza um objeto de <xref:System.Xml.XPath.XPathNodeIterator> como um parâmetro. Este método de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> de detalhe é idêntico ao método de <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> que utiliza apenas um objeto de <xref:System.Xml.XPath.XPathExpression> como um parâmetro, exceto que permite que a um nó do argumento especifica o contexto atual para executar sobre a avaliação. Este contexto é necessário para o XPath `position()` e funções de `last()` que são relativos ao nó atual de contexto. A menos que usado como um predicado em uma etapa local, `position()` e funções de `last()` requerem uma referência a um nó definida para ser avaliado de outra forma, `position` e funções `last`de retorno de `0` .  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Xml.XmlDocument>  
- <xref:System.Xml.XPath.XPathDocument>  
- <xref:System.Xml.XPath.XPathNavigator>  
- [Processar dados XML usando o modelo de dados XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
- [Selecionar dados XML usando XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
- [Correspondência de nós usando XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
- [Tipos de nós reconhecidos com consultas XPath](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
- [Consultas e Namespaces de XPath](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
- [Expressões XPath compilados](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
