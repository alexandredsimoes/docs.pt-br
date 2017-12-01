---
title: Atributos em controles dos Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 21f39aa1f85e06f1967d278e07731b73dcf7cb10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="attributes-in-windows-forms-controls"></a><span data-ttu-id="e41f7-102">Atributos em controles dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e41f7-102">Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="e41f7-103">O .NET Framework fornece uma variedade de atributos que podem se aplicados aos membros de seus controles personalizados e componentes.</span><span class="sxs-lookup"><span data-stu-id="e41f7-103">The .NET Framework provides a variety of attributes you can apply to the members of your custom controls and components.</span></span> <span data-ttu-id="e41f7-104">Alguns desses atributos afetam o comportamento de uma classe no tempo de execução, enquanto outros afetam o comportamento no tempo de design.</span><span class="sxs-lookup"><span data-stu-id="e41f7-104">Some of these attributes affect the run-time behavior of a class, and others affect the design-time behavior.</span></span>  
  
## <a name="attributes-for-control-and-component-properties"></a><span data-ttu-id="e41f7-105">Atributos de propriedades de controles e componentes</span><span class="sxs-lookup"><span data-stu-id="e41f7-105">Attributes for Control and Component Properties</span></span>  
 <span data-ttu-id="e41f7-106">A tabela a seguir mostra os atributos que podem ser aplicados a propriedades ou outros membros de seus controles e componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="e41f7-106">The following table shows the attributes you can apply to properties or other members of your custom controls and components.</span></span> <span data-ttu-id="e41f7-107">Para ver um exemplo que usa muitos desses atributos, consulte [Como aplicar atributos a controles dos Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e41f7-107">For an example that uses many of these attributes, see [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
|<span data-ttu-id="e41f7-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e41f7-108">Attribute</span></span>|<span data-ttu-id="e41f7-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e41f7-109">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|<span data-ttu-id="e41f7-110">Especifica o valor a ser passado para uma propriedade para fazer com que a propriedade obtenha o seu valor de outra origem.</span><span class="sxs-lookup"><span data-stu-id="e41f7-110">Specifies the value to pass to a property to cause the property to get its value from another source.</span></span> <span data-ttu-id="e41f7-111">Isso é conhecido como *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="e41f7-111">This is known as *ambience*.</span></span>|  
|<xref:System.ComponentModel.BrowsableAttribute>|<span data-ttu-id="e41f7-112">Especifica se uma propriedade ou evento deve ser exibido em uma janela **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e41f7-112">Specifies whether a property or event should be displayed in a **Properties** window.</span></span>|  
|<xref:System.ComponentModel.CategoryAttribute>|<span data-ttu-id="e41f7-113">Especifica o nome da categoria na qual grupo de propriedade ou evento quando exibido em uma <xref:System.Windows.Forms.PropertyGrid> controle definido como <xref:System.Windows.Forms.PropertySort.Categorized> modo.</span><span class="sxs-lookup"><span data-stu-id="e41f7-113">Specifies the name of the category in which to group the property or event when displayed in a <xref:System.Windows.Forms.PropertyGrid> control set to <xref:System.Windows.Forms.PropertySort.Categorized> mode.</span></span>|  
|<xref:System.ComponentModel.DefaultValueAttribute>|<span data-ttu-id="e41f7-114">Especifica o valor padrão de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="e41f7-114">Specifies the default value for a property.</span></span>|  
|<xref:System.ComponentModel.DescriptionAttribute>|<span data-ttu-id="e41f7-115">Especifica uma descrição de uma propriedade ou evento.</span><span class="sxs-lookup"><span data-stu-id="e41f7-115">Specifies a description for a property or event.</span></span>|  
|<xref:System.ComponentModel.DisplayNameAttribute>|<span data-ttu-id="e41f7-116">Especifica o nome de exibição de uma propriedade, evento ou método `public``void` que não usa argumentos.</span><span class="sxs-lookup"><span data-stu-id="e41f7-116">Specifies the display name for a property, event, or `public``void` method that takes no arguments.</span></span>|  
|<xref:System.ComponentModel.EditorAttribute>|<span data-ttu-id="e41f7-117">Especifica o editor que deve ser usado para alterar uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="e41f7-117">Specifies the editor to use to change a property.</span></span>|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|<span data-ttu-id="e41f7-118">Especifica que uma propriedade ou método é visível em um editor.</span><span class="sxs-lookup"><span data-stu-id="e41f7-118">Specifies that a property or method is viewable in an editor.</span></span>|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|<span data-ttu-id="e41f7-119">Especifica a palavra-chave de contexto de uma classe ou membro.</span><span class="sxs-lookup"><span data-stu-id="e41f7-119">Specifies the context keyword for a class or member.</span></span>|  
|<xref:System.ComponentModel.LocalizableAttribute>|<span data-ttu-id="e41f7-120">Especifica se uma propriedade deve ser localizada.</span><span class="sxs-lookup"><span data-stu-id="e41f7-120">Specifies whether a property should be localized.</span></span>|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|<span data-ttu-id="e41f7-121">Indica que a representação de texto de um objeto é obscurecida por caracteres como asteriscos.</span><span class="sxs-lookup"><span data-stu-id="e41f7-121">Indicates that an object's text representation is obscured by characters such as asterisks.</span></span>|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|<span data-ttu-id="e41f7-122">Especifica se a propriedade à qual esse atributo está associado é somente leitura ou leitura/gravação no tempo de design.</span><span class="sxs-lookup"><span data-stu-id="e41f7-122">Specifies whether the property this attribute is bound to is read-only or read/write at design time.</span></span>|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|<span data-ttu-id="e41f7-123">Indica que a grade de propriedades deve ser atualizada quando o valor da propriedade associada é alterado.</span><span class="sxs-lookup"><span data-stu-id="e41f7-123">Indicates that the property grid should refresh when the associated property value changes.</span></span>|  
|<xref:System.ComponentModel.TypeConverterAttribute>|<span data-ttu-id="e41f7-124">Especifica o tipo a ser usado como um conversor para o objeto ao qual este atributo está associado.</span><span class="sxs-lookup"><span data-stu-id="e41f7-124">Specifies what type to use as a converter for the object this attribute is bound to.</span></span>|  
  
## <a name="attributes-for-data-binding-properties"></a><span data-ttu-id="e41f7-125">Atributos para propriedades de vinculação de dados</span><span class="sxs-lookup"><span data-stu-id="e41f7-125">Attributes for Data Binding Properties</span></span>  
 <span data-ttu-id="e41f7-126">A tabela a seguir mostra os atributos que podem ser aplicados para especificar como os controles e componentes personalizados interagem com vinculação de dados.</span><span class="sxs-lookup"><span data-stu-id="e41f7-126">The following table shows the attributes you can apply to specify how your custom controls and components interact with data binding.</span></span>  
  
|<span data-ttu-id="e41f7-127">Atributo</span><span class="sxs-lookup"><span data-stu-id="e41f7-127">Attribute</span></span>|<span data-ttu-id="e41f7-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="e41f7-128">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|<span data-ttu-id="e41f7-129">Especifica se uma propriedade normalmente é usada para associação.</span><span class="sxs-lookup"><span data-stu-id="e41f7-129">Specifies whether a property is typically used for binding.</span></span>|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|<span data-ttu-id="e41f7-130">Especifica a fonte de dados e as propriedades de membro de dados para um componente.</span><span class="sxs-lookup"><span data-stu-id="e41f7-130">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|<span data-ttu-id="e41f7-131">Especifica a propriedade de associação padrão de um componente.</span><span class="sxs-lookup"><span data-stu-id="e41f7-131">Specifies the default binding property for a component.</span></span>|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|<span data-ttu-id="e41f7-132">Especifica a fonte de dados e as propriedades de membro de dados para um componente.</span><span class="sxs-lookup"><span data-stu-id="e41f7-132">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|<span data-ttu-id="e41f7-133">Habilita o redirecionamento de atributo.</span><span class="sxs-lookup"><span data-stu-id="e41f7-133">Enables attribute redirection.</span></span>|  
  
## <a name="attributes-for-classes"></a><span data-ttu-id="e41f7-134">Atributos para classes</span><span class="sxs-lookup"><span data-stu-id="e41f7-134">Attributes for Classes</span></span>  
 <span data-ttu-id="e41f7-135">A tabela a seguir mostra os atributos que podem ser aplicados para especificar o comportamento dos seus controles e componentes personalizados no tempo de design.</span><span class="sxs-lookup"><span data-stu-id="e41f7-135">The following table shows the attributes you can apply to specify the behavior of your custom controls and components at design time.</span></span>  
  
|<span data-ttu-id="e41f7-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="e41f7-136">Attribute</span></span>|<span data-ttu-id="e41f7-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="e41f7-137">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|<span data-ttu-id="e41f7-138">Especifica o evento padrão de um componente.</span><span class="sxs-lookup"><span data-stu-id="e41f7-138">Specifies the default event for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|<span data-ttu-id="e41f7-139">Especifica a propriedade padrão de um componente.</span><span class="sxs-lookup"><span data-stu-id="e41f7-139">Specifies the default property for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerAttribute>|<span data-ttu-id="e41f7-140">Especifica a classe usada para implementar os serviços de tempo de design para um componente.</span><span class="sxs-lookup"><span data-stu-id="e41f7-140">Specifies the class used to implement design-time services for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|<span data-ttu-id="e41f7-141">Especifica que o designer de uma classe pertence a uma determinada categoria.</span><span class="sxs-lookup"><span data-stu-id="e41f7-141">Specifies that the designer for a class belongs to a certain category.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|<span data-ttu-id="e41f7-142">Representa um atributo de um item de caixa de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e41f7-142">Represents an attribute of a toolbox item.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|<span data-ttu-id="e41f7-143">Especifica a cadeia de caracteres de filtro e o tipo de filtro para um item de Caixa de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e41f7-143">Specifies the filter string and filter type to use for a Toolbox item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e41f7-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e41f7-144">See Also</span></span>  
 <xref:System.Attribute>  
 [<span data-ttu-id="e41f7-145">Como aplicar atributos a controles dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e41f7-145">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="e41f7-146">Estendendo o suporte ao tempo de design</span><span class="sxs-lookup"><span data-stu-id="e41f7-146">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="e41f7-147">Desenvolvendo controles dos Windows Forms personalizados com o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e41f7-147">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)