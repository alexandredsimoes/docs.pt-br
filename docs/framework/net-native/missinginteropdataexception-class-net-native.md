---
title: Classe MissingInteropDataException (.NET Nativo)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 540ffc4aba7150c8ccac31b23162f35fec416f44
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="missinginteropdataexception-class-net-native"></a>Classe MissingInteropDataException (.NET Nativo)
**.NET para Aplicativos da Windows Store para Windows 10, somente [!INCLUDE[net_native](../../../includes/net-native-md.md)]**  
  
 A exceção que é acionada quando um método de marshaling manual é chamado, mas os metadados de um tipo não são encontrados por análise estática ou em um arquivo de diretivas de tempo de execução.  
  
 **Namespace:** System.Runtime.CompilerServices  
  
> [!IMPORTANT]
>  A classe `MissingInteropDataException` destina-se somente para uso interno da cadeia de ferramentas [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Ela não é destinado para uso em código de terceiros e você também não deve tratar a exceção no seu código do aplicativo. Em vez disso, elimine a exceção adicionando entradas ao seu [arquivo de diretivas de tempo de execução](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Para obter mais informações, consulte a seção Comentários.  
  
## <a name="syntax"></a>Sintaxe  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)] [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 A classe `MissingInteropDataException` tem os seguintes membros:  
  
## <a name="constructors"></a>Construtores  
  
|Construtor|Descrição|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|Inicializa uma nova instância da classe `MissingInteropDataException` usando a ID de uma mensagem fornecida pelo sistema que descreve o erro e o tipo cujos dados estão ausentes. Esse construtor destina-se ao uso interno somente pela cadeia de ferramentas [!INCLUDE[net_native](../../../includes/net-native-md.md)].|  
  
## <a name="properties"></a>Propriedades  
  
|Propriedade|Descrição|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Obtém uma coleção de pares de chave/valor que fornecem informações adicionais definidas pelo usuário sobre a exceção. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public string HelpLink { get; set; }`|Obtém ou define um link para o arquivo de ajuda associado a essa exceção. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public int HResult { get; protected set; }`|Obtém ou define o `HRESULT`, que é um valor numérico codificado atribuído a uma exceção específica. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public Exception InnerException { get; }`|Obtém a exceção que causou a exceção atual. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public string Message { get; }`|Obtém uma mensagem que descreve a exceção atual. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public Type MissingType { get; private set; }`|Obtém ou define o tipo cujos dados estão ausentes.|  
|`public string Source { get; set; }`|Obtém ou define o nome do aplicativo ou objeto que causou o erro. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public string StackTrace { get; }`|Obtém uma representação de cadeia de caracteres de quadros imediatos na pilha de chamadas. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public MethodBase TargetSite { get; }`|Obtém o método que acionou a exceção atual. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Determina se o objeto especificado é igual ao objeto atual.  (Herdado de <xref:System.Object>.)|  
|`protected void Finalize()`|Permite que um objeto tente liberar recursos e executar outras operações de limpeza antes de ser recuperado pela coleta de lixo. (Herdado de <xref:System.Object>.)|  
|`public Exception GetBaseException()`|Retorna a exceção é a causa raiz de uma ou mais exceções subsequentes. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public int GetHashCode()`|Retorna um código de hash para uma instância `MissingInteropDataException`.   (Herdado de <xref:System.Object>.)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Define um objeto <xref:System.Runtime.Serialization.SerializationInfo> com informações sobre a exceção.  (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`public Type GetType()`|Obtém o tipo de tempo de execução da instância atual. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
|`protected Object MemberwiseClone()`|Cria uma cópia superficial do objeto atual. (Herdado de <xref:System.Object>.)|  
|`public string ToString()`|Retorna a representação de cadeia de caracteres de exceção atual. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
  
## <a name="events"></a>Eventos  
  
|Evento|Descrição|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Ocorre quando uma exceção é serializada para criar um objeto de estado de exceção que contém dados serializados sobre a exceção. (Herdado de <xref:System.Exception?displayProperty=fullName>.)|  
  
## <a name="usage-details"></a>Detalhes de uso  
 A exceção `MissingInteropDataException` é acionada quando uma chamada de método para um componente COM ou do Tempo de Execução do Windows não pode ser concluída com êxito porque as informações de tipo não estão disponíveis.  
  
 Os metadados disponíveis em um aplicativo no tempo de execução é definido pelo arquivo de diretivas (configuração XML) de tempo de execução, *. rd.xml. Para impedir que o seu aplicativo gere esta exceção, você deve modificar este arquivo para definir os metadados que devem estar presentes no tempo de execução. Geralmente, esse erro é tratado adicionando um atributo `MarshalObject`, `MarshalDelegate` ou `MarshalStructure` a um elemento de programa apropriado no arquivo de diretivas de tempo de execução. Para obter informações sobre o formato desse arquivo, consulte [Referência do arquivo de configuração das diretivas de tempo de execução (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  Como essa exceção indica que os metadados exigidos pelo seu aplicativo não estão disponíveis no tempo de execução, você não deve tratar essa exceção em um bloco `try`/`catch`. Em vez disso, você deve diagnosticar a causa da exceção e eliminá-la adicionando a entrada apropriada a um arquivo de diretivas de tempo de execução.  
  
 A classe `MissingInteropDataException` contém um único membro exclusivo, a propriedade `MissingType`, que indica o tipo cujos metadados são necessários para concluir uma chamada de método com êxito. Todos os membros restantes são herdados da classe base, <xref:System.Exception?displayProperty=fullName>.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Exception?displayProperty=fullName>   
 [Classe MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)   
 [Referência do arquivo de configuração das diretivas de tempo de execução (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
