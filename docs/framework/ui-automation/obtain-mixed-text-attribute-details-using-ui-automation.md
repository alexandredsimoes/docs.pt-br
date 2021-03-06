---
title: Obter detalhes de atributos de texto misto usando automação de interface do usuário
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 8b7d3519a9f106a6679a9b2a404ed400bb6ae4a1
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856719"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a>Obter detalhes de atributos de texto misto usando automação de interface do usuário
> [!NOTE]
>  Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>. Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).  
  
 Este tópico mostra como usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para obter detalhes de atributos de texto de um intervalo de texto que abrange vários valores de atributo. Um intervalo de texto pode corresponder ao local atual do cursor (ou a seleção de degeneração) dentro de um documento, uma seleção contígua de texto, uma coleção de seleções de texto não contíguos ou todo o conteúdo textual de um documento.  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir demonstra como obter o <xref:System.Windows.Automation.TextPattern.FontNameAttribute> de um intervalo de texto em que <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> retorna um <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> objeto.  
  
 [!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
 [!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 O <xref:System.Windows.Automation.TextPattern> padrão de controle, em tandem com o <xref:System.Windows.Automation.Text.TextPatternRange> classe, dá suporte a atributos de texto básico, propriedades e métodos. Para a funcionalidade específica do controle que não é compatível com <xref:System.Windows.Automation.TextPattern> ou <xref:System.Windows.Automation.Text.TextPatternRange>, o <xref:System.Windows.Automation.AutomationElement> classe fornece métodos para um cliente de automação de interface do usuário acessar o modelo de objeto nativo correspondente.  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral de TextPattern de automação de interface do usuário](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [Adicionar conteúdo a uma caixa de texto utilizando automação da interface do usuário](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [Localizar e destacar texto usando automação de interface do usuário](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [Visão geral de padrões de controle de automação da interface do usuário](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Padrões de controle de automação de interface do usuário para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Obter atributos de texto usando automação de interface do usuário](../../../docs/framework/ui-automation/obtain-text-attributes-using-ui-automation.md)
