---
title: Assinar eventos de automação de interface do usuário
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: c6845a85f9d3e07a4ecc9aad1ec11df8cdbc1f7a
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706233"
---
# <a name="subscribe-to-ui-automation-events"></a>Assinar eventos de automação de interface do usuário
> [!NOTE]
>  Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>. Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).  
  
 Este tópico mostra como assinar eventos gerados por provedores de automação de interface do usuário.  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir registra um manipulador de eventos para o evento que é gerado quando um controle como um botão é invocado e o remove quando fecha o formulário do aplicativo. O evento é identificado por um <xref:System.Windows.Automation.AutomationEvent> passado como um parâmetro para <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para assinar um evento que é gerado quando o foco é alterado. O manipulador de eventos é não registrado em um método que poderia ser chamado no encerramento do aplicativo, ou quando a notificação de eventos de interface do usuário não é mais necessária.  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>  
 [Visão geral sobre eventos de automação de interface do usuário](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
