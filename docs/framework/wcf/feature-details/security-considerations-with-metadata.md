---
title: "Considerações de segurança com metadados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e78ef8ab-4f63-4656-ab93-b1deab2666d5
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 75191aa28be76da549d38403c4a6f019c6f54bc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="security-considerations-with-metadata"></a><span data-ttu-id="2d70c-102">Considerações de segurança com metadados</span><span class="sxs-lookup"><span data-stu-id="2d70c-102">Security Considerations with Metadata</span></span>
<span data-ttu-id="2d70c-103">Quando usar os metadados de recursos no [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], considere as implicações de segurança de publicação, recuperar e usando metadados de serviço.</span><span class="sxs-lookup"><span data-stu-id="2d70c-103">When using the metadata features in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], consider the security implications of publishing, retrieving, and using service metadata.</span></span>  
  
## <a name="when-to-publish-metadata"></a><span data-ttu-id="2d70c-104">Quando publicar metadados</span><span class="sxs-lookup"><span data-stu-id="2d70c-104">When to Publish Metadata</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2d70c-105">serviços não publicar metadados por padrão.</span><span class="sxs-lookup"><span data-stu-id="2d70c-105"> services do not publish metadata by default.</span></span> <span data-ttu-id="2d70c-106">Para publicar metadados para um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] você deve habilitar explicitamente a publicação de metadados com a adição de pontos de extremidade de metadados para o serviço de serviço (consulte [metadados de publicação](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)).</span><span class="sxs-lookup"><span data-stu-id="2d70c-106">To publish metadata for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service you must explicitly enable metadata publishing by adding metadata endpoints to your service (see [Publishing Metadata](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)).</span></span> <span data-ttu-id="2d70c-107">Publicação de metadados desabilitada reduz a superfície de ataque para o serviço e reduz o risco de divulgação de informações não intencionais.</span><span class="sxs-lookup"><span data-stu-id="2d70c-107">Leaving metadata publishing disabled reduces the attack surface for your service and lowers the risk of unintentional information disclosure.</span></span> <span data-ttu-id="2d70c-108">Nem todos os serviços devem publicar metadados.</span><span class="sxs-lookup"><span data-stu-id="2d70c-108">Not all services must publish metadata.</span></span> <span data-ttu-id="2d70c-109">Se você não precisa publicar metadados, considere deixá-la desativado.</span><span class="sxs-lookup"><span data-stu-id="2d70c-109">If you do not have to publish metadata, consider leaving it turned off.</span></span> <span data-ttu-id="2d70c-110">Observe que você ainda pode gerar o código de cliente e metadados diretamente de seus conjuntos de serviço usando o [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2d70c-110">Note that you can still generate metadata and client code directly from your service assemblies using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="2d70c-111">usar o Svcutil.exe para exportar metadados, consulte [como: usar a Svcutil.exe para exportar metadados de código de serviço compilado](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md).</span><span class="sxs-lookup"><span data-stu-id="2d70c-111"> using Svcutil.exe to export metadata, see [How to: Use Svcutil.exe to Export Metadata from Compiled Service Code](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md).</span></span>  
  
## <a name="publishing-metadata-using-a-secure-binding"></a><span data-ttu-id="2d70c-112">Metadados de publicação usando uma associação de segurança</span><span class="sxs-lookup"><span data-stu-id="2d70c-112">Publishing Metadata Using a Secure Binding</span></span>  
 <span data-ttu-id="2d70c-113">As associações de metadados padrão que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornece não são seguro e permitir acesso anônimo aos metadados.</span><span class="sxs-lookup"><span data-stu-id="2d70c-113">The default metadata bindings that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides are not secure and they allow anonymous access to the metadata.</span></span> <span data-ttu-id="2d70c-114">Os metadados de serviço que um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviço publica contém uma descrição detalhada sobre o serviço e podem intencionalmente ou não conter informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="2d70c-114">The service metadata that a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service publishes contains a detailed description about the service and may intentionally or unintentionally contain sensitive information.</span></span> <span data-ttu-id="2d70c-115">Por exemplo, os metadados de serviço podem conter informações sobre as operações de infra-estrutura que não foi desenvolvidas para ser transmitida publicamente.</span><span class="sxs-lookup"><span data-stu-id="2d70c-115">For example, service metadata may contain information about infrastructure operations that was not intended to be broadcast publicly.</span></span> <span data-ttu-id="2d70c-116">Para proteger os metadados de serviço contra acesso não autorizado, você pode usar uma associação de segurança para seu ponto de extremidade de metadados.</span><span class="sxs-lookup"><span data-stu-id="2d70c-116">To protect service metadata from unauthorized access, you can use a secure binding for your metadata endpoint.</span></span> <span data-ttu-id="2d70c-117">Pontos de extremidade de metadados respondem a solicitações HTTP/GET que podem usar o SSL Secure Sockets Layer () para proteger os metadados.</span><span class="sxs-lookup"><span data-stu-id="2d70c-117">Metadata endpoints respond to HTTP/GET requests that can use Secure Sockets Layer (SSL) to secure the metadata.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="2d70c-118">[Como: proteger pontos de extremidade de metadados](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="2d70c-118"> [How to: Secure Metadata Endpoints](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md).</span></span>  
  
 <span data-ttu-id="2d70c-119">Proteger os pontos de extremidade de metadados também fornece uma maneira para que os solicitantes de recuperar metadados de serviço sem o risco de falsificação ou violação.</span><span class="sxs-lookup"><span data-stu-id="2d70c-119">Securing your metadata endpoints also provides a way for requesters to securely retrieve service metadata without the risk of tampering or spoofing.</span></span>  
  
## <a name="using-only-trusted-metadata"></a><span data-ttu-id="2d70c-120">Usando somente confiáveis metadados</span><span class="sxs-lookup"><span data-stu-id="2d70c-120">Using Only Trusted Metadata</span></span>  
 <span data-ttu-id="2d70c-121">Você pode usar os metadados de serviço para construir automaticamente os componentes de tempo de execução necessários para chamar o serviço.</span><span class="sxs-lookup"><span data-stu-id="2d70c-121">You can use service metadata to automatically construct the run-time components required to call the service.</span></span> <span data-ttu-id="2d70c-122">Você também pode usar metadados em tempo de design para desenvolver um aplicativo cliente ou em tempo de execução para atualizar dinamicamente a associação de um cliente usa para chamar um serviço.</span><span class="sxs-lookup"><span data-stu-id="2d70c-122">You can also use metadata at design time to develop a client application or at runtime to dynamically update the binding a client uses to call a service.</span></span>  
  
 <span data-ttu-id="2d70c-123">Metadados de serviço podem ser violados ou falsificados quando recuperados de uma maneira segura.</span><span class="sxs-lookup"><span data-stu-id="2d70c-123">Service metadata can be tampered with or spoofed when retrieved in an insecure manner.</span></span> <span data-ttu-id="2d70c-124">Metadados violado podem redirecionar o cliente para um serviço mal-intencionado, contêm configurações de segurança comprometido ou conter mal-intencionado estruturas XML.</span><span class="sxs-lookup"><span data-stu-id="2d70c-124">Tampered metadata can redirect your client to a malicious service, contain compromised security settings, or contain malicious XML structures.</span></span> <span data-ttu-id="2d70c-125">Documentos de metadados podem ser grandes e frequentemente são salvos no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2d70c-125">Metadata documents can be large and are frequently saved to the file system.</span></span> <span data-ttu-id="2d70c-126">Para proteger contra violações e falsificações, use uma associação de segurança para solicitar metadados de serviço quando houver uma disponível.</span><span class="sxs-lookup"><span data-stu-id="2d70c-126">To protect against tampering and spoofing, use a secure binding to request service metadata when one is available.</span></span>  
  
## <a name="using-safe-techniques-for-processing-metadata"></a><span data-ttu-id="2d70c-127">Usando técnicas de seguras para o processamento de metadados</span><span class="sxs-lookup"><span data-stu-id="2d70c-127">Using Safe Techniques for Processing Metadata</span></span>  
 <span data-ttu-id="2d70c-128">Metadados de serviço com frequência são recuperados de um serviço em uma rede usando protocolos padronizados, como WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="2d70c-128">Service metadata is frequently retrieved from a service over a network using standardized protocols such as WS-MetadataExchange (MEX).</span></span> <span data-ttu-id="2d70c-129">Vários formatos de metadados incluem mecanismos para apontar para metadados adicionais de referência.</span><span class="sxs-lookup"><span data-stu-id="2d70c-129">Many metadata formats include referencing mechanisms for pointing to additional metadata.</span></span> <span data-ttu-id="2d70c-130">O <xref:System.ServiceModel.Description.MetadataExchangeClient> tipo processa automaticamente as referências para você em documentos WSDL Web Services Description Language (), o esquema XML e documentos MEX.</span><span class="sxs-lookup"><span data-stu-id="2d70c-130">The <xref:System.ServiceModel.Description.MetadataExchangeClient> type automatically processes references for you in Web Services Description Language (WSDL) documents, XML Schema, and MEX documents.</span></span> <span data-ttu-id="2d70c-131">O tamanho do <xref:System.ServiceModel.Description.MetadataSet> objeto criado a partir de metadados recuperados é diretamente proporcional ao <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> valor para o <xref:System.ServiceModel.Description.MetadataExchangeClient> instância é usada e o `MaxReceivedMessageSize` valor para a associação está sendo usada por que <xref:System.ServiceModel.Description.MetadataExchangeClient> instância.</span><span class="sxs-lookup"><span data-stu-id="2d70c-131">The size of the <xref:System.ServiceModel.Description.MetadataSet> object created from the retrieved metadata is directly proportional to the <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> value for the <xref:System.ServiceModel.Description.MetadataExchangeClient> instance that is used and the `MaxReceivedMessageSize` value for the binding being used by that <xref:System.ServiceModel.Description.MetadataExchangeClient> instance.</span></span> <span data-ttu-id="2d70c-132">Defina essas cotas para os valores apropriados, conforme determinado pelo seu cenário.</span><span class="sxs-lookup"><span data-stu-id="2d70c-132">Set these quotas to appropriate values as dictated by your scenario.</span></span>  
  
 <span data-ttu-id="2d70c-133">Em [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], metadados de serviço é processado como XML.</span><span class="sxs-lookup"><span data-stu-id="2d70c-133">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], service metadata is processed as XML.</span></span> <span data-ttu-id="2d70c-134">Durante o processamento de documentos XML, aplicativos devem se proteger contra mal-intencionado estruturas XML.</span><span class="sxs-lookup"><span data-stu-id="2d70c-134">When processing XML documents, applications should protect themselves against malicious XML structures.</span></span> <span data-ttu-id="2d70c-135">Use o `XmlDictionaryReader` com apropriado cotas durante o processamento de XML e também definir o <xref:System.Xml.XmlTextReader.DtdProcessing%2A> propriedade `Prohibit`.</span><span class="sxs-lookup"><span data-stu-id="2d70c-135">Use the `XmlDictionaryReader` with appropriate quotas when processing XML and also set the <xref:System.Xml.XmlTextReader.DtdProcessing%2A> property to `Prohibit`.</span></span>  
  
 <span data-ttu-id="2d70c-136">O sistema de metadados em [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] é extensível e as extensões de metadados podem ser registradas em seu arquivo de configuração do aplicativo (consulte [estendendo o sistema de metadados](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)).</span><span class="sxs-lookup"><span data-stu-id="2d70c-136">The metadata system in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is extensible and metadata extensions can be registered in your application configuration file (see [Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)).</span></span> <span data-ttu-id="2d70c-137">Extensões de metadados podem executar um código arbitrário, para que você deve proteger seu arquivo de configuração do aplicativo com o controle de acesso apropriadas de ACLs e registrar apenas os metadados confiável implementações de extensão.</span><span class="sxs-lookup"><span data-stu-id="2d70c-137">Metadata extensions can run arbitrary code, so you should protect your application configuration file with appropriate access control lists (ACLs) and register only trusted metadata extension implementations.</span></span>  
  
## <a name="validating-generated-clients"></a><span data-ttu-id="2d70c-138">Validando clientes gerados</span><span class="sxs-lookup"><span data-stu-id="2d70c-138">Validating Generated Clients</span></span>  
 <span data-ttu-id="2d70c-139">Ao gerar o código do cliente de metadados recuperados de uma fonte que não é confiável, valide o código de cliente gerada para garantir que o cliente gerado está em conformidade com as políticas de segurança de aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="2d70c-139">When generating client code from metadata retrieved from a source that is not trusted, validate the generated client code to ensure that the generated client conforms to your client applications security policies.</span></span> <span data-ttu-id="2d70c-140">Você pode usar um comportamento de validação para verificar as configurações no seu cliente de associação ou inspecionar visualmente o código gerado por ferramentas.</span><span class="sxs-lookup"><span data-stu-id="2d70c-140">You can use a validating behavior to check settings on your client binding or visually inspect code generated by tools.</span></span> <span data-ttu-id="2d70c-141">Para obter um exemplo de como implementar um cliente que valida os comportamentos, consulte [validação do cliente](../../../../docs/framework/wcf/samples/client-validation.md).</span><span class="sxs-lookup"><span data-stu-id="2d70c-141">For an example of how to implement a client that validates behaviors, see [Client Validation](../../../../docs/framework/wcf/samples/client-validation.md).</span></span>  
  
## <a name="protecting-application-configuration-files"></a><span data-ttu-id="2d70c-142">Protegendo arquivos de configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="2d70c-142">Protecting Application Configuration Files</span></span>  
 <span data-ttu-id="2d70c-143">Arquivo de configuração de aplicativo do serviço pode controlar como e se os metadados são publicados.</span><span class="sxs-lookup"><span data-stu-id="2d70c-143">A service's application configuration file may control how and if metadata is published.</span></span> <span data-ttu-id="2d70c-144">É uma boa ideia para proteger o arquivo de configuração do aplicativo com listas de controle de acesso adequadas (ACLs) para garantir que o invasor não pode modificar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="2d70c-144">It is a good idea to protect the application configuration file with appropriate access control lists (ACLs) to ensure an attacker cannot modify such settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d70c-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2d70c-145">See Also</span></span>  
 [<span data-ttu-id="2d70c-146">Como: proteger pontos de extremidade de metadados</span><span class="sxs-lookup"><span data-stu-id="2d70c-146">How to: Secure Metadata Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md)  
 [<span data-ttu-id="2d70c-147">Segurança</span><span class="sxs-lookup"><span data-stu-id="2d70c-147">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)