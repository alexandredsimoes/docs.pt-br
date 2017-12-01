---
title: "Visão geral das propriedades de automação da interface do usuário"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
caps.latest.revision: "17"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: a6fec422e235413bd76d86cdcb5a72a351bb3f97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="344c3-102">Visão geral das propriedades de automação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="344c3-102">UI Automation Properties Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="344c3-103">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="344c3-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="344c3-104">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="344c3-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="344c3-105">Provedores de automação de interface do usuário expõem propriedades em [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementos.</span><span class="sxs-lookup"><span data-stu-id="344c3-105">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="344c3-106">Essas propriedades permitem que aplicativos clientes de automação de interface do usuário descobrir informações sobre partes do [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especialmente controla, incluindo dados estáticos e dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="344c3-106">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="344c3-107">Esta seção fornece uma visão geral das [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] propriedades.</span><span class="sxs-lookup"><span data-stu-id="344c3-107">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="344c3-108">Informações mais específicas são fornecidas nos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="344c3-108">More specific information is given in the following topics:</span></span>  
  
-   [<span data-ttu-id="344c3-109">Propriedades de automação de interface do usuário para clientes</span><span class="sxs-lookup"><span data-stu-id="344c3-109">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
  
-   [<span data-ttu-id="344c3-110">Implementação de provedor de Automação da Interface do Usuário no lado do servidor</span><span class="sxs-lookup"><span data-stu-id="344c3-110">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>   
## <a name="property-identifiers"></a><span data-ttu-id="344c3-111">Identificadores de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-111">Property Identifiers</span></span>  
 <span data-ttu-id="344c3-112">Cada propriedade é identificada por um número e um nome.</span><span class="sxs-lookup"><span data-stu-id="344c3-112">Every property is identified by a number and a name.</span></span> <span data-ttu-id="344c3-113">Os nomes das propriedades são usados somente para depuração e diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="344c3-113">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="344c3-114">Os provedores de usar o valor numérico [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] para identificar solicitações de propriedade recebidas.</span><span class="sxs-lookup"><span data-stu-id="344c3-114">Providers use the numeric [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] to identify incoming property requests.</span></span> <span data-ttu-id="344c3-115">Aplicativos cliente, no entanto, apenas usam <xref:System.Windows.Automation.AutomationProperty>, que encapsula o número e o nome, para identificar as propriedades desejam recuperar.</span><span class="sxs-lookup"><span data-stu-id="344c3-115">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="344c3-116"><xref:System.Windows.Automation.AutomationProperty>objetos que representam propriedades particulares estão disponíveis como campos de várias classes.</span><span class="sxs-lookup"><span data-stu-id="344c3-116"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="344c3-117">Por motivos de segurança, provedores de automação de interface de usuário obtêm esses objetos de um conjunto separado de classes que estão contidos em UIAutomationTypes.</span><span class="sxs-lookup"><span data-stu-id="344c3-117">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="344c3-118">A tabela a seguir categoriza as propriedades pelas classes que contêm o <xref:System.Windows.Automation.AutomationProperty> [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="344c3-118">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>[!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)].</span></span>  
  
|<span data-ttu-id="344c3-119">Tipos de propriedades</span><span class="sxs-lookup"><span data-stu-id="344c3-119">Kinds of properties</span></span>|<span data-ttu-id="344c3-120">Os clientes obtêm as IDs do</span><span class="sxs-lookup"><span data-stu-id="344c3-120">Clients get IDs from</span></span>|<span data-ttu-id="344c3-121">Provedores de obtém as IDs do</span><span class="sxs-lookup"><span data-stu-id="344c3-121">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="344c3-122">Propriedades comuns a todos os elementos (veja a seguir de tabelas)</span><span class="sxs-lookup"><span data-stu-id="344c3-122">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="344c3-123">Posição de uma janela de encaixe</span><span class="sxs-lookup"><span data-stu-id="344c3-123">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="344c3-124">Estado de um elemento que pode expandir e recolher</span><span class="sxs-lookup"><span data-stu-id="344c3-124">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="344c3-125">Propriedades de um item em uma grade</span><span class="sxs-lookup"><span data-stu-id="344c3-125">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="344c3-126">Propriedades de uma grade</span><span class="sxs-lookup"><span data-stu-id="344c3-126">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="344c3-127">Exibição atual e com suporte de um elemento que tem vários modos de exibição</span><span class="sxs-lookup"><span data-stu-id="344c3-127">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="344c3-128">Propriedades de um elemento que se move sobre um intervalo de valores, como um controle deslizante</span><span class="sxs-lookup"><span data-stu-id="344c3-128">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="344c3-129">Propriedades de uma janela de rolagem</span><span class="sxs-lookup"><span data-stu-id="344c3-129">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="344c3-130">Status e o contêiner de um item que pode ser selecionado, como uma lista</span><span class="sxs-lookup"><span data-stu-id="344c3-130">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="344c3-131">Propriedades de um controle que contém a seleção de itens</span><span class="sxs-lookup"><span data-stu-id="344c3-131">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="344c3-132">Cabeçalhos de coluna e linha de um item em uma tabela</span><span class="sxs-lookup"><span data-stu-id="344c3-132">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="344c3-133">Cabeçalhos de coluna e linha e a orientação, de uma tabela</span><span class="sxs-lookup"><span data-stu-id="344c3-133">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="344c3-134">Estado de um controle de alternância</span><span class="sxs-lookup"><span data-stu-id="344c3-134">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="344c3-135">Recursos de um elemento que podem ser movidos, girados, ou redimensionados</span><span class="sxs-lookup"><span data-stu-id="344c3-135">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="344c3-136">Recursos de valor e leitura/gravação de um elemento que tem um valor</span><span class="sxs-lookup"><span data-stu-id="344c3-136">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="344c3-137">Recursos e estado de uma janela</span><span class="sxs-lookup"><span data-stu-id="344c3-137">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>   
## <a name="properties-by-category"></a><span data-ttu-id="344c3-138">Propriedades por categoria</span><span class="sxs-lookup"><span data-stu-id="344c3-138">Properties by Category</span></span>  
 <span data-ttu-id="344c3-139">As tabelas a seguir categorizam as propriedades cujo [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] são encontrados em <xref:System.Windows.Automation.AutomationElement> e <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span><span class="sxs-lookup"><span data-stu-id="344c3-139">The following tables categorize the properties whose [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="344c3-140">Essas propriedades são comuns a todos os controles.</span><span class="sxs-lookup"><span data-stu-id="344c3-140">These properties are common to all controls.</span></span> <span data-ttu-id="344c3-141">Tudo, exceto alguns deles devem ser estáticos sobre o tempo de vida do aplicativo provedor; propriedades dinâmicas mais são associadas com os padrões de controle.</span><span class="sxs-lookup"><span data-stu-id="344c3-141">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="344c3-142">O **acesso de propriedade** coluna lista quaisquer outros acessadores para cada propriedade, além <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> e <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="344c3-142">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="344c3-143">Para obter mais informações sobre a obtenção de propriedades em um aplicativo cliente, consulte [propriedades de automação de interface do usuário para clientes](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="344c3-143">For more information on getting properties in a client application, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="344c3-144">Para obter informações específicas sobre cada propriedade, siga o link no **acesso de propriedade** coluna.</span><span class="sxs-lookup"><span data-stu-id="344c3-144">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="344c3-145">Características de exibição</span><span class="sxs-lookup"><span data-stu-id="344c3-145">Display Characteristics</span></span>  
  
|<span data-ttu-id="344c3-146">Identificador de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-146">Property identifier</span></span>|<span data-ttu-id="344c3-147">Acesso de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-147">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="344c3-148">N/D</span><span class="sxs-lookup"><span data-stu-id="344c3-148">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="344c3-149">Tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="344c3-149">Element Type</span></span>  
  
|<span data-ttu-id="344c3-150">Identificador de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-150">Property identifier</span></span>|<span data-ttu-id="344c3-151">Acesso de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-151">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="344c3-152">Identificação</span><span class="sxs-lookup"><span data-stu-id="344c3-152">Identification</span></span>  
  
|<span data-ttu-id="344c3-153">Identificador de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-153">Property identifier</span></span>|<span data-ttu-id="344c3-154">Acesso de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-154">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="344c3-155">Interação</span><span class="sxs-lookup"><span data-stu-id="344c3-155">Interaction</span></span>  
  
|<span data-ttu-id="344c3-156">Identificador de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-156">Property identifier</span></span>|<span data-ttu-id="344c3-157">Acesso de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-157">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="344c3-158">Suporte para padrões</span><span class="sxs-lookup"><span data-stu-id="344c3-158">Support for Patterns</span></span>  
  
|<span data-ttu-id="344c3-159">Identificador de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-159">Property identifier</span></span>|<span data-ttu-id="344c3-160">Acesso de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-160">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="344c3-161">Diversos</span><span class="sxs-lookup"><span data-stu-id="344c3-161">Miscellaneous</span></span>  
  
|<span data-ttu-id="344c3-162">Identificador de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-162">Property identifier</span></span>|<span data-ttu-id="344c3-163">Acesso de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-163">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>   
## <a name="localization"></a><span data-ttu-id="344c3-164">Localização</span><span class="sxs-lookup"><span data-stu-id="344c3-164">Localization</span></span>  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="344c3-165">provedores devem apresentar as seguintes propriedades no idioma do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="344c3-165"> providers should present the following properties in the language of the operating system:</span></span>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
-   <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>   
## <a name="properties-and-events"></a><span data-ttu-id="344c3-166">Propriedades e eventos</span><span class="sxs-lookup"><span data-stu-id="344c3-166">Properties and Events</span></span>  
 <span data-ttu-id="344c3-167">Intimamente vinculado às propriedades na [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] é o conceito de eventos de propriedade alterada.</span><span class="sxs-lookup"><span data-stu-id="344c3-167">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="344c3-168">Para propriedades dinâmicas, o aplicativo cliente precisa de uma maneira de saber que um valor de propriedade foi alterado, para que ele possa atualizar seu cache de informações ou reagir às novas informações de alguma outra maneira.</span><span class="sxs-lookup"><span data-stu-id="344c3-168">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="344c3-169">Provedores geram eventos quando algo a [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] alterações.</span><span class="sxs-lookup"><span data-stu-id="344c3-169">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="344c3-170">Por exemplo, se uma caixa de seleção é marcada ou desmarcada, um evento de propriedade alterada é gerado pela implementação do provedor do padrão de alternância.</span><span class="sxs-lookup"><span data-stu-id="344c3-170">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="344c3-171">Provedores podem gerar eventos seletivamente, dependendo se todos os clientes são escuta para eventos ou de escuta para eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="344c3-171">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="344c3-172">Nem todas as alterações de propriedade geram eventos; que é definido inteiramente a implementação do provedor de automação de interface do usuário para o elemento.</span><span class="sxs-lookup"><span data-stu-id="344c3-172">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="344c3-173">Por exemplo, os provedores de proxy padrão para caixas de listagem não geram um evento quando o <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> alterações.</span><span class="sxs-lookup"><span data-stu-id="344c3-173">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="344c3-174">Nesse caso, o aplicativo deve escutar para uma <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span><span class="sxs-lookup"><span data-stu-id="344c3-174">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="344c3-175">Os clientes escutam eventos inscrevendo-se a eles.</span><span class="sxs-lookup"><span data-stu-id="344c3-175">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="344c3-176">Assinando eventos significa criar métodos representantes que podem manipular os eventos e, em seguida, passar os métodos para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] juntamente com os eventos específicos que serão tratados nesses métodos.</span><span class="sxs-lookup"><span data-stu-id="344c3-176">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="344c3-177">Para eventos de propriedade alterada em particular, os clientes devem implementar <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="344c3-177">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344c3-178">Consulte também</span><span class="sxs-lookup"><span data-stu-id="344c3-178">See Also</span></span>  
 [<span data-ttu-id="344c3-179">Armazenamento em cache em clientes de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="344c3-179">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)  
 [<span data-ttu-id="344c3-180">Propriedades de automação de interface do usuário para clientes</span><span class="sxs-lookup"><span data-stu-id="344c3-180">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="344c3-181">Implementação de provedor de Automação da Interface do Usuário no lado do servidor</span><span class="sxs-lookup"><span data-stu-id="344c3-181">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)  
 [<span data-ttu-id="344c3-182">Localizar um elemento de automação de interface do usuário com base em uma condição de propriedade</span><span class="sxs-lookup"><span data-stu-id="344c3-182">Find a UI Automation Element Based on a Property Condition</span></span>](../../../docs/framework/ui-automation/find-a-ui-automation-element-based-on-a-property-condition.md)  
 [<span data-ttu-id="344c3-183">Retornar as propriedades de um provedor de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="344c3-183">Return Properties from a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/return-properties-from-a-ui-automation-provider.md)  
 [<span data-ttu-id="344c3-184">Disparar eventos de um provedor de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="344c3-184">Raise Events from a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/raise-events-from-a-ui-automation-provider.md)