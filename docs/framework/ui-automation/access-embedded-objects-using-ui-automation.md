---
title: "Acessar objetos inseridos usando automação de interface de usuário"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
caps.latest.revision: "17"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0f417acd3440c224db06ca4034c23a1cd6eb395e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="c979d-102">Acessar objetos inseridos usando automação de interface de usuário</span><span class="sxs-lookup"><span data-stu-id="c979d-102">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="c979d-103">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c979d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c979d-104">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="c979d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c979d-105">Este tópico mostra como [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] pode ser usada para expor objetos inseridos dentro do conteúdo de um controle de texto.</span><span class="sxs-lookup"><span data-stu-id="c979d-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c979d-106">Objetos inseridos podem incluir imagens, hiperlinks, botões, tabelas ou controles ActiveX.</span><span class="sxs-lookup"><span data-stu-id="c979d-106">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="c979d-107">Objetos inseridos são considerados filhos do [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] provedor de texto.</span><span class="sxs-lookup"><span data-stu-id="c979d-107">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="c979d-108">Isso permite que eles sejam expostos pela estrutura de árvore de automação de interface do usuário como todos os outros [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elementos.</span><span class="sxs-lookup"><span data-stu-id="c979d-108">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="c979d-109">Funcionalidade, por sua vez, é exposta através de padrões de controle normalmente pelo tipo de controle de objetos inseridos (por exemplo, como os hiperlinks são baseados em texto, suportarão <xref:System.Windows.Automation.TextPattern>).</span><span class="sxs-lookup"><span data-stu-id="c979d-109">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="c979d-110">![Objetos inseridos em um contêiner de texto. ] (../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="c979d-110">![Embedded objects in a text container.](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="c979d-111">Um documento de exemplo com conteúdo textual ("Você sabia?" ...) e dois objetos inseridos (uma imagem de um baleia e um hiperlink de texto), usados como um destino para os exemplos de código.</span><span class="sxs-lookup"><span data-stu-id="c979d-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c979d-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c979d-112">Example</span></span>  
 <span data-ttu-id="c979d-113">O exemplo de código a seguir demonstra como recuperar uma coleção de objetos inseridos de dentro um [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] provedor de texto.</span><span class="sxs-lookup"><span data-stu-id="c979d-113">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="c979d-114">O documento de exemplo fornecido na introdução, dois objetos seriam retornados (um elemento de imagem e um elemento de texto).</span><span class="sxs-lookup"><span data-stu-id="c979d-114">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c979d-115">O elemento de imagem deve ter algum texto intrínseco associado a ele que descreva a imagem, normalmente em seu <xref:System.Windows.Automation.AutomationElement.NameProperty> (por exemplo, "Uma baleia azul.").</span><span class="sxs-lookup"><span data-stu-id="c979d-115">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="c979d-116">No entanto, quando um intervalo de texto abrangendo o objeto de imagem é obtido, nem a imagem nem esse texto descritivo é retornado no fluxo de texto.</span><span class="sxs-lookup"><span data-stu-id="c979d-116">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="c979d-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c979d-117">Example</span></span>  
 <span data-ttu-id="c979d-118">O exemplo de código a seguir demonstra como obter um intervalo de texto de um objeto inserido em um [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] provedor de texto.</span><span class="sxs-lookup"><span data-stu-id="c979d-118">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="c979d-119">O intervalo de texto recuperado é um intervalo vazio onde o ponto de extremidade inicial segue "...</span><span class="sxs-lookup"><span data-stu-id="c979d-119">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="c979d-120">oceano. (espaço) "e o ponto de extremidade final precede o". "que representa o hiperlink inserido (como mostrado pela imagem exibida na Introdução).</span><span class="sxs-lookup"><span data-stu-id="c979d-120">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="c979d-121">Embora esse seja um intervalo vazio, ele não é considerado um intervalo degenerado porque ele tem uma extensão diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="c979d-121">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c979d-122"><xref:System.Windows.Automation.TextPattern>pode recuperar um objeto inserido baseado em texto, como um hiperlink; No entanto, um secundário <xref:System.Windows.Automation.TextPattern> terá que ser obtido a partir do objeto inserido para expor sua funcionalidade completa.</span><span class="sxs-lookup"><span data-stu-id="c979d-122"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="c979d-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c979d-123">See Also</span></span>  
 [<span data-ttu-id="c979d-124">Visão geral de TextPattern de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="c979d-124">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="c979d-125">Visão geral de padrões de controle de automação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="c979d-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="c979d-126">Padrões de controle de automação de interface do usuário para clientes</span><span class="sxs-lookup"><span data-stu-id="c979d-126">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="c979d-127">Adicionar conteúdo a um Text Box utilizando Automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="c979d-127">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="c979d-128">Encontre e destaque texto usando automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="c979d-128">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)