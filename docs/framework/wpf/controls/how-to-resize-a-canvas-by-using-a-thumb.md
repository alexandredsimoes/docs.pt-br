---
title: Como redimensionar uma tela usando um elevador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: be267e832180b49686079f426dfa5c30ffdd81b0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518057"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Como redimensionar uma tela usando um elevador
Este exemplo mostra como usar um <xref:System.Windows.Controls.Primitives.Thumb> controle para redimensionar um <xref:System.Windows.Controls.Canvas> controle.  
  
## <a name="example"></a>Exemplo  
 O <xref:System.Windows.Controls.Primitives.Thumb> controle fornece funcionalidade de arrastar que pode ser usada para mover ou redimensionar controles monitorando os <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> eventos do <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 O usuário começa uma operação de arrastar pressionando o botão esquerdo do mouse quando o ponteiro do mouse está em pausa sobre o <xref:System.Windows.Controls.Primitives.Thumb> controle. A operação de arrastar continuará enquanto o botão esquerdo do mouse permanecer pressionado. Durante a operação de arrastar, o <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> pode ocorrer mais de uma vez. Cada vez que ele ocorre, o <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> classe fornece a alteração de posição que corresponde à alteração na posição do mouse. Quando o usuário libera o botão esquerdo do mouse, a operação de arrastar é concluída. A operação de arrastar fornece somente novas coordenadas; não reposicionar automaticamente o <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 A exemplo a seguir mostra uma <xref:System.Windows.Controls.Primitives.Thumb> controle que é o elemento filho de um <xref:System.Windows.Controls.Canvas> controle. O manipulador de eventos para seus <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> evento fornece a lógica para mover o <xref:System.Windows.Controls.Primitives.Thumb> e redimensione o <xref:System.Windows.Controls.Canvas>. Os manipuladores de eventos para o <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> evento alterar a cor do <xref:System.Windows.Controls.Primitives.Thumb> durante uma operação de arrastar. O exemplo a seguir define o <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 A exemplo a seguir mostra a <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> manipulador de eventos que move os <xref:System.Windows.Controls.Primitives.Thumb> e redimensiona o <xref:System.Windows.Controls.Canvas> em resposta a um movimento do mouse.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 A exemplo a seguir mostra o <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> manipulador de eventos.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 A exemplo a seguir mostra o <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> manipulador de eventos.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Para o exemplo completo, consulte [Exemplo de funcionalidade de arrastar do elevador](https://go.microsoft.com/fwlink/?LinkID=160042).  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
