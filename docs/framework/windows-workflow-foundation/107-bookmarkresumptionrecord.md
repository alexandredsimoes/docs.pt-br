---
title: 107 -- BookmarkResumptionRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 247a439dcbe566e74fd0157fbd92b9cb6c96e375
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="107----bookmarkresumptionrecord"></a><span data-ttu-id="776d7-102">107 -- BookmarkResumptionRecord</span><span class="sxs-lookup"><span data-stu-id="776d7-102">107 -- BookmarkResumptionRecord</span></span>
## <a name="properties"></a><span data-ttu-id="776d7-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="776d7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="776d7-104">Id</span><span class="sxs-lookup"><span data-stu-id="776d7-104">Id</span></span>|<span data-ttu-id="776d7-105">107</span><span class="sxs-lookup"><span data-stu-id="776d7-105">107</span></span>|  
|<span data-ttu-id="776d7-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="776d7-106">Keywords</span></span>|<span data-ttu-id="776d7-107">EndToEndMonitoring, solução de problemas, HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="776d7-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="776d7-108">Nível</span><span class="sxs-lookup"><span data-stu-id="776d7-108">Level</span></span>|<span data-ttu-id="776d7-109">Informações</span><span class="sxs-lookup"><span data-stu-id="776d7-109">Information</span></span>|  
|<span data-ttu-id="776d7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="776d7-110">Channel</span></span>|<span data-ttu-id="776d7-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="776d7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="776d7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="776d7-112">Description</span></span>  
 <span data-ttu-id="776d7-113">Este evento é emitido pelo participante de rastreamento de ETW quando uma instância de fluxo de trabalho se emite um BookmarkResumptionRecord.</span><span class="sxs-lookup"><span data-stu-id="776d7-113">This event is emitted by the ETW tracking participant when a workflow instance emits a BookmarkResumptionRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="776d7-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="776d7-114">Message</span></span>  
 <span data-ttu-id="776d7-115">TrackRecord = BookmarkResumptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, nome = %4, SubInstanceID = %5, OwnerActivityName = %6, OwnerActivityId = %7, OwnerActivityInstanceId = %8, OwnerActivityTypeName = %9, anotações = % 10, ProfileName = % 11</span><span class="sxs-lookup"><span data-stu-id="776d7-115">TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5,  OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11</span></span>  
  
## <a name="details"></a><span data-ttu-id="776d7-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="776d7-116">Details</span></span>  
  
|<span data-ttu-id="776d7-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="776d7-117">Data Item Name</span></span>|<span data-ttu-id="776d7-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="776d7-118">Data Item Type</span></span>|<span data-ttu-id="776d7-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="776d7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="776d7-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="776d7-120">InstanceId</span></span>|<span data-ttu-id="776d7-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="776d7-121">xs:GUID</span></span>|<span data-ttu-id="776d7-122">A identificação de instância para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="776d7-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="776d7-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="776d7-123">RecordNumber</span></span>|<span data-ttu-id="776d7-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="776d7-124">xs:long</span></span>|<span data-ttu-id="776d7-125">O número de sequência do registro emitido</span><span class="sxs-lookup"><span data-stu-id="776d7-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="776d7-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="776d7-126">EventTime</span></span>|<span data-ttu-id="776d7-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="776d7-127">xs:dateTime</span></span>|<span data-ttu-id="776d7-128">A hora UTC quando o evento foi emitido</span><span class="sxs-lookup"><span data-stu-id="776d7-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="776d7-129">Nome</span><span class="sxs-lookup"><span data-stu-id="776d7-129">Name</span></span>|<span data-ttu-id="776d7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-130">xs:string</span></span>|<span data-ttu-id="776d7-131">O nome do indexador que foi que</span><span class="sxs-lookup"><span data-stu-id="776d7-131">The name of the bookmark that was resumed</span></span>|  
|<span data-ttu-id="776d7-132">SubInstanceID</span><span class="sxs-lookup"><span data-stu-id="776d7-132">SubInstanceID</span></span>|<span data-ttu-id="776d7-133">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="776d7-133">xs:GUID</span></span>|<span data-ttu-id="776d7-134">A identificação do escopo do indexador</span><span class="sxs-lookup"><span data-stu-id="776d7-134">The id of the bookmark scope</span></span>|  
|<span data-ttu-id="776d7-135">OwnerActivityName</span><span class="sxs-lookup"><span data-stu-id="776d7-135">OwnerActivityName</span></span>|<span data-ttu-id="776d7-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-136">xs:string</span></span>|<span data-ttu-id="776d7-137">O nome de atividade do indexador</span><span class="sxs-lookup"><span data-stu-id="776d7-137">The name of the bookmark activity</span></span>|  
|<span data-ttu-id="776d7-138">OwnerActivityId</span><span class="sxs-lookup"><span data-stu-id="776d7-138">OwnerActivityId</span></span>|<span data-ttu-id="776d7-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-139">xs:string</span></span>|<span data-ttu-id="776d7-140">A identificação de atividade do indexador</span><span class="sxs-lookup"><span data-stu-id="776d7-140">The id of the bookmark activity</span></span>|  
|<span data-ttu-id="776d7-141">OwnerActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="776d7-141">OwnerActivityInstanceId</span></span>|<span data-ttu-id="776d7-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-142">xs:string</span></span>|<span data-ttu-id="776d7-143">A identificação de instância de atividade do indexador</span><span class="sxs-lookup"><span data-stu-id="776d7-143">The instance id of the bookmark activity</span></span>|  
|<span data-ttu-id="776d7-144">OwnerActivityTypeName</span><span class="sxs-lookup"><span data-stu-id="776d7-144">OwnerActivityTypeName</span></span>|<span data-ttu-id="776d7-145">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-145">xs:string</span></span>|<span data-ttu-id="776d7-146">O tipo de atividade do indexador</span><span class="sxs-lookup"><span data-stu-id="776d7-146">The type of the bookmark activity</span></span>|  
|<span data-ttu-id="776d7-147">Anotações</span><span class="sxs-lookup"><span data-stu-id="776d7-147">Annotations</span></span>|<span data-ttu-id="776d7-148">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-148">xs:string</span></span>|<span data-ttu-id="776d7-149">As anotações que foram adicionadas a este evento.</span><span class="sxs-lookup"><span data-stu-id="776d7-149">The annotations that were added to this event.</span></span>  <span data-ttu-id="776d7-150">Os valores são armazenados em um elemento xml no formato \<itens >\< nome do item = "annotationName" type="System.String" > annotationValue\</item > \< /itens >.</span><span class="sxs-lookup"><span data-stu-id="776d7-150">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="776d7-151">Se nenhuma anotação é especificada, em seguida, a cadeia de caracteres contém \<itens / >.</span><span class="sxs-lookup"><span data-stu-id="776d7-151">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="776d7-152">O tamanho do evento de ETW é limitado pelo tamanho do buffer de ETW ou pela carga máxima útil para um evento de ETW.</span><span class="sxs-lookup"><span data-stu-id="776d7-152">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="776d7-153">Se o tamanho do evento excede os limites ETW, o evento é truncado descartando as anotações e substituindo o valor anotação com \<itens >...  \< /itens >.</span><span class="sxs-lookup"><span data-stu-id="776d7-153">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="776d7-154">ProfileName</span><span class="sxs-lookup"><span data-stu-id="776d7-154">ProfileName</span></span>|<span data-ttu-id="776d7-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-155">xs:string</span></span>|<span data-ttu-id="776d7-156">O nome ou o perfil de rastreamento que levam a este evento que está sendo emitido</span><span class="sxs-lookup"><span data-stu-id="776d7-156">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="776d7-157">HostReference</span><span class="sxs-lookup"><span data-stu-id="776d7-157">HostReference</span></span>|<span data-ttu-id="776d7-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-158">xs:string</span></span>|<span data-ttu-id="776d7-159">Hospedados para serviços da Web, este campo identifica unicamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="776d7-159">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="776d7-160">O formato é definido como ' caminho Virtual do aplicativo de nome de Site da Web &#124; Caminho Virtual do serviço &#124; ServiceName' exemplo: ' Default Web Site/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'</span><span class="sxs-lookup"><span data-stu-id="776d7-160">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="776d7-161">AppDomain</span><span class="sxs-lookup"><span data-stu-id="776d7-161">AppDomain</span></span>|<span data-ttu-id="776d7-162">xs:string</span><span class="sxs-lookup"><span data-stu-id="776d7-162">xs:string</span></span>|<span data-ttu-id="776d7-163">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="776d7-163">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|