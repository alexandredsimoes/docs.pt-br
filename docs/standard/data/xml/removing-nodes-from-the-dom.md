---
title: Removendo os nós DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be592466627e6ee7b23c608e0defe786548907ad
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206987"
---
# <a name="removing-nodes-from-the-dom"></a>Removendo os nós DOM
Para remover um nó de (DOM) modelo de objeto de documento, use o método de <xref:System.Xml.XmlNode.RemoveChild%2A> para remover um nó específico. Quando você remove um nó, o método remove a subárvore que pertence ao nó que está sendo removido; isto é, se não é um nó folha.  
  
 Para remover os vários nós DOM, use o método de <xref:System.Xml.XmlNode.RemoveAll%2A> para remover todos os filhos e atributos, se aplicável, do nó atual.  
  
 Se você estiver trabalhando com <xref:System.Xml.XmlNamedNodeMap>, você pode remover um nó usando o método <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> .  
  
 Para remover os atributos, confira [Removendo os atributos de um nó no elemento DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>Consulte também

- [DOM (Modelo de Objeto do Documento) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
