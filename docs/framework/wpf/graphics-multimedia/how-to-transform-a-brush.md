---
title: Como transformar um pincel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: ebc8d4c6cb36d76b70691cce183f9e6070d19822
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507041"
---
# <a name="how-to-transform-a-brush"></a>Como transformar um pincel
Este exemplo mostra como transformar <xref:System.Windows.Media.Brush> objetos usando suas duas propriedades de transformação: <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 Os exemplos seguintes usam um <xref:System.Windows.Media.RotateTransform> girar o conteúdo de um <xref:System.Windows.Media.ImageBrush> em 45 graus.  
  
 A ilustração a seguir mostra a <xref:System.Windows.Media.ImageBrush> sem uma <xref:System.Windows.Media.RotateTransform>, com o <xref:System.Windows.Media.RotateTransform> aplicado ao <xref:System.Windows.Media.Brush.RelativeTransform%2A> propriedade e com o <xref:System.Windows.Media.RotateTransform> aplicadas ao <xref:System.Windows.Media.Brush.Transform%2A> propriedade.  
  
 ![Brush RelativeTransform and Transform settings](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Exemplo  
 O primeiro exemplo aplica um <xref:System.Windows.Media.RotateTransform> para o <xref:System.Windows.Media.Brush.RelativeTransform%2A> propriedade de um <xref:System.Windows.Media.ImageBrush>. O <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> propriedades de um <xref:System.Windows.Media.RotateTransform> do objeto são definidas como 0,5, que é a coordenada relativa do ponto central deste conteúdo. Como resultado, o <xref:System.Windows.Media.ImageBrush> conteúdo gira sobre seu centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 O segundo exemplo também se aplica uma <xref:System.Windows.Media.RotateTransform> para um <xref:System.Windows.Media.ImageBrush>; no entanto, este exemplo usa o <xref:System.Windows.Media.Brush.Transform%2A> propriedade em vez do <xref:System.Windows.Media.Brush.RelativeTransform%2A> propriedade.  
  
 Para girar o pincel sobre seu centro, o exemplo define o <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> propriedades do <xref:System.Windows.Media.RotateTransform> objeto como coordenadas absolutas. Como o pincel pinta um retângulo de 175 x 90 pixels, o ponto central do retângulo é (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Para obter uma descrição de como o <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> propriedades funcionam, consulte o [visão geral da transformação de pincel](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Para obter o exemplo completo, consulte [Exemplo de pincéis](https://go.microsoft.com/fwlink/?LinkID=159973). Para obter mais informações sobre pincéis, consulte [Visão geral da pintura com cores sólidas e gradientes](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral da transformação de pincel](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [Visão geral da pintura com cores sólidas e gradientes](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Visão geral de transformações](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
