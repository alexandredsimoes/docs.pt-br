---
title: XAML no WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AutoGeneratedOrientationPage
helpviewer_keywords:
- XAML [WPF]
- Extensible Application Markup Language [WPF]
ms.assetid: 5d858575-a83b-42df-ad3f-047ed2d6e3c8
caps.latest.revision: "79"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 74f5a19e891bf0b86f91fcbe4f6b59b4d6acc8bb
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="xaml-in-wpf"></a><span data-ttu-id="974c7-102">XAML no WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-102">XAML in WPF</span></span>
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="974c7-103">é uma linguagem de marcação para aplicativos de programação.</span><span class="sxs-lookup"><span data-stu-id="974c7-103"> is a markup language for declarative application programming.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="974c7-104">implementa a implementação do processador aXAML e fornece suporte de linguagem XAML.</span><span class="sxs-lookup"><span data-stu-id="974c7-104"> implements aXAML processor implementation, and provides XAML language support.</span></span> <span data-ttu-id="974c7-105">O [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipos são implementados, de modo que eles possam fornecer o tipo necessário fazendo para uma representação de XAML.</span><span class="sxs-lookup"><span data-stu-id="974c7-105">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] types are implemented such that they can provide the required type backing for a XAML representation.</span></span> <span data-ttu-id="974c7-106">Em geral, você pode criar a maior parte do seu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] da interface do usuário do aplicativo na marcação XAML.</span><span class="sxs-lookup"><span data-stu-id="974c7-106">In general, you can create the majority of your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application UI in XAML markup.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="974c7-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="974c7-107">In This Section</span></span>  
 [<span data-ttu-id="974c7-108">Visão geral de XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="974c7-108">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="974c7-109">Sintaxe XAML em detalhes</span><span class="sxs-lookup"><span data-stu-id="974c7-109">XAML Syntax In Detail</span></span>](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)  
 [<span data-ttu-id="974c7-110">Code-behind e XAML no WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-110">Code-Behind and XAML in WPF</span></span>](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="974c7-111">XAML e classes personalizadas para WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-111">XAML and Custom Classes for WPF</span></span>](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [<span data-ttu-id="974c7-112">Extensões de marcação e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-112">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="974c7-113">Namespaces XAML e mapeamento de namespace para XAML WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-113">XAML Namespaces and Namespace Mapping for WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)  
 [<span data-ttu-id="974c7-114">Namescopes XAML WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-114">WPF XAML Namescopes</span></span>](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [<span data-ttu-id="974c7-115">Modelos e estilos embutidos</span><span class="sxs-lookup"><span data-stu-id="974c7-115">Inline Styles and Templates</span></span>](../../../../docs/framework/wpf/advanced/inline-styles-and-templates.md)  
 [<span data-ttu-id="974c7-116">Processamento de Espaço em branco em XAML</span><span class="sxs-lookup"><span data-stu-id="974c7-116">Whitespace Processing in XAML</span></span>](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="974c7-117">TypeConverters e XAML</span><span class="sxs-lookup"><span data-stu-id="974c7-117">TypeConverters and XAML</span></span>](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [<span data-ttu-id="974c7-118">Entidades e XAML de caractere XML</span><span class="sxs-lookup"><span data-stu-id="974c7-118">XML Character Entities and XAML</span></span>](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)  
 [<span data-ttu-id="974c7-119">Recursos da linguagem (x:) do namespace de XAML</span><span class="sxs-lookup"><span data-stu-id="974c7-119">XAML Namespace (x:) Language Features</span></span>](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [<span data-ttu-id="974c7-120">Extensões XAML WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-120">WPF XAML Extensions</span></span>](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [<span data-ttu-id="974c7-121">Recursos de linguagem da compatibilidade de marcação (mc:)</span><span class="sxs-lookup"><span data-stu-id="974c7-121">Markup Compatibility (mc:) Language Features</span></span>](../../../../docs/framework/wpf/advanced/markup-compatibility-mc-language-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="974c7-122">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="974c7-122">Related Sections</span></span>  
 [<span data-ttu-id="974c7-123">Arquitetura do WPF</span><span class="sxs-lookup"><span data-stu-id="974c7-123">WPF Architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  [<span data-ttu-id="974c7-124">Elementos base</span><span class="sxs-lookup"><span data-stu-id="974c7-124">Base Elements</span></span>](../../../../docs/framework/wpf/advanced/base-elements.md)  
  [<span data-ttu-id="974c7-125">Árvore de elementos e serialização</span><span class="sxs-lookup"><span data-stu-id="974c7-125">Element Tree and Serialization</span></span>](../../../../docs/framework/wpf/advanced/element-tree-and-serialization.md)  
  [<span data-ttu-id="974c7-126">Propriedades</span><span class="sxs-lookup"><span data-stu-id="974c7-126">Properties</span></span>](../../../../docs/framework/wpf/advanced/properties-wpf.md)  
  [<span data-ttu-id="974c7-127">Eventos</span><span class="sxs-lookup"><span data-stu-id="974c7-127">Events</span></span>](../../../../docs/framework/wpf/advanced/events-wpf.md)  
  [<span data-ttu-id="974c7-128">Entrada</span><span class="sxs-lookup"><span data-stu-id="974c7-128">Input</span></span>](../../../../docs/framework/wpf/advanced/input-wpf.md)  
  [<span data-ttu-id="974c7-129">Recursos</span><span class="sxs-lookup"><span data-stu-id="974c7-129">Resources</span></span>](../../../../docs/framework/wpf/advanced/resources-wpf.md)  
  [<span data-ttu-id="974c7-130">Estilo e modelagem</span><span class="sxs-lookup"><span data-stu-id="974c7-130">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
  [<span data-ttu-id="974c7-131">Modelo de threading</span><span class="sxs-lookup"><span data-stu-id="974c7-131">Threading Model</span></span>](../../../../docs/framework/wpf/advanced/threading-model.md)