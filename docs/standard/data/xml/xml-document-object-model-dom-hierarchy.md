---
title: Hierarquia DOM (Document Object Model) XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef2b5b200f95cdfac9b08a33c328c1dfb797e59e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274655"
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Hierarquia DOM (Document Object Model) XML
A ilustração a seguir mostra a hierarquia de classes para o DOM (Document Object Model) XML, com o nome do World Wide Web Consortium (W3C) entre parênteses junto com o nome da classe onde é relevante.  
  
 ![Modelo de objeto de documento XML &#40;DOM&#41; hierarquia](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Hierarquia DOM (Document Object Model) XML  
  
 As seguintes classes não herdam de **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 A classe **XmlImplementation** é usada para criar um documento XML. Para saber mais, confira [Criação de documento XML](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 A classe **XmlNamedNodeMap** manipula um conjunto não ordenado de nós. Para saber mais, confira [Recuperação não ordenada de nós por nome ou índice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 A classe **XmlNodeList** manipula uma lista ordenada de nós. Para saber mais, confira [Recuperação ordenada de nós por índice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 A classe **XmlNodeChangedEventArgs** manipula os manipuladores de eventos registrados em **XmlDocument**. Para saber mais, confira [Manipulação de eventos em um documento XML usando XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 A classe **XmlLinkedNode** herda de **XmlNode**. Sua finalidade é substituir dois métodos de **XmlNode**: os métodos **PreviousSibling** e **NextSibling**. Esses métodos substituídos são então herdados e usados por **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** e **XmlProcessingInstruction**, que são classes que têm irmãos anteriores e seguintes.  
  
## <a name="see-also"></a>Consulte também

- [DOM (Modelo de Objeto do Documento) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
