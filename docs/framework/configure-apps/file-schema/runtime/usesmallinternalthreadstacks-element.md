---
title: '&lt;UseSmallInternalThreadStacks&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2558423b412333a4d6ac9f650ad8ff3dab449d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a><span data-ttu-id="d858e-102">&lt;UseSmallInternalThreadStacks&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="d858e-102">&lt;UseSmallInternalThreadStacks&gt; Element</span></span>
<span data-ttu-id="d858e-103">Solicitações que o common language runtime (CLR) reduzir memória usam com a especificação de tamanhos de pilha explícita ao criar determinados threads que ele usa internamente, em vez de usar o tamanho da pilha padrão para esses threads.</span><span class="sxs-lookup"><span data-stu-id="d858e-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="d858e-104">\<Configuração > elemento</span><span class="sxs-lookup"><span data-stu-id="d858e-104">\<configuration> Element</span></span>  
<span data-ttu-id="d858e-105">\<tempo de execução > elemento</span><span class="sxs-lookup"><span data-stu-id="d858e-105">\<runtime> Element</span></span>  
<span data-ttu-id="d858e-106">\<UseSmallInternalThreadStacks > elemento</span><span class="sxs-lookup"><span data-stu-id="d858e-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d858e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d858e-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d858e-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d858e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d858e-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="d858e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d858e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d858e-110">Attributes</span></span>  
  
|<span data-ttu-id="d858e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d858e-111">Attribute</span></span>|<span data-ttu-id="d858e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="d858e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d858e-113">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d858e-113">enabled</span></span>|<span data-ttu-id="d858e-114">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d858e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="d858e-115">Especifica se deve solicitar que os tamanhos de pilha explícita de uso CLR em vez do tamanho da pilha padrão ao criar determinados threads que ele usa internamente.</span><span class="sxs-lookup"><span data-stu-id="d858e-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="d858e-116">Os tamanhos de pilha explícitas são menores que o tamanho da pilha padrão de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="d858e-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d858e-117">Atributo habilitado</span><span class="sxs-lookup"><span data-stu-id="d858e-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="d858e-118">Valor</span><span class="sxs-lookup"><span data-stu-id="d858e-118">Value</span></span>|<span data-ttu-id="d858e-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="d858e-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d858e-120">true</span><span class="sxs-lookup"><span data-stu-id="d858e-120">true</span></span>|<span data-ttu-id="d858e-121">Tamanhos de pilha explícita de solicitações.</span><span class="sxs-lookup"><span data-stu-id="d858e-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="d858e-122">false</span><span class="sxs-lookup"><span data-stu-id="d858e-122">false</span></span>|<span data-ttu-id="d858e-123">Use o tamanho da pilha padrão.</span><span class="sxs-lookup"><span data-stu-id="d858e-123">Use the default stack size.</span></span> <span data-ttu-id="d858e-124">Esse é o padrão para o [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d858e-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d858e-125">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d858e-125">Child Elements</span></span>  
 <span data-ttu-id="d858e-126">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d858e-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d858e-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d858e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d858e-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d858e-128">Element</span></span>|<span data-ttu-id="d858e-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="d858e-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d858e-130">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d858e-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d858e-131">Contém informações sobre associação do assembly e coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="d858e-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d858e-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="d858e-132">Remarks</span></span>  
 <span data-ttu-id="d858e-133">Este elemento de configuração é usado para solicitar o uso de memória virtual reduzido em um processo, porque os tamanhos de thread explícita que o CLR usa para seus threads internos, se a solicitação for respeitada, são menores que o tamanho padrão.</span><span class="sxs-lookup"><span data-stu-id="d858e-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d858e-134">Este elemento de configuração é uma solicitação para o CLR, em vez de um requisito absoluto.</span><span class="sxs-lookup"><span data-stu-id="d858e-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="d858e-135">No [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a solicitação é respeitada somente para x86 arquitetura.</span><span class="sxs-lookup"><span data-stu-id="d858e-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="d858e-136">Esse elemento pode ser completamente ignorado em versões futuras do CLR ou substituído por tamanhos de pilha explícitas são sempre usados para threads internos selecionados.</span><span class="sxs-lookup"><span data-stu-id="d858e-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="d858e-137">Especificando a que este elemento de configuração negocia confiabilidade para menor uso de memória virtual se o CLR honra a solicitação, porque os tamanhos menores de pilha potencialmente podem tornar a pilha estoura mais provável.</span><span class="sxs-lookup"><span data-stu-id="d858e-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d858e-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d858e-138">Example</span></span>  
 <span data-ttu-id="d858e-139">O exemplo a seguir mostra como solicitar que a pilha explícita de uso do CLR para determinados tamanhos de threads que ele usa internamente.</span><span class="sxs-lookup"><span data-stu-id="d858e-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d858e-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d858e-140">See Also</span></span>  
 [<span data-ttu-id="d858e-141">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="d858e-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d858e-142">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="d858e-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)