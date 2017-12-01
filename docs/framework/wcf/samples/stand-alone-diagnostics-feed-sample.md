---
title: "Exemplo de feed de diagnóstico independente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c95a2e1e1790633df77e7c4ecd6603e68321e478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="stand-alone-diagnostics-feed-sample"></a><span data-ttu-id="ee36d-102">Exemplo de feed de diagnóstico independente</span><span class="sxs-lookup"><span data-stu-id="ee36d-102">Stand-Alone Diagnostics Feed Sample</span></span>
<span data-ttu-id="ee36d-103">Este exemplo demonstra como criar um feed de distribuição com RSS/Atom [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee36d-103">This sample demonstrates how to create an RSS/Atom feed for syndication with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="ee36d-104">É um programa "Hello World" básico que mostra os fundamentos de como o modelo de objeto e como configurá-lo em um [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] serviço.</span><span class="sxs-lookup"><span data-stu-id="ee36d-104">It is a basic "Hello World" program that shows the basics of the object model and how to set it up on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ee36d-105">modelos de feeds de agregação como operações de serviço que retornam um tipo de dados especial <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="ee36d-105"> models syndication feeds as service operations that return a special data type, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="ee36d-106">Instâncias do <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> pode serializar um feed em formatos de RSS 2.0 e Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="ee36d-106">Instances of <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> can serialize a feed into both the RSS 2.0 and Atom 1.0 formats.</span></span> <span data-ttu-id="ee36d-107">O código de exemplo a seguir mostra o contrato usado.</span><span class="sxs-lookup"><span data-stu-id="ee36d-107">The following sample code shows the contract used.</span></span>  
  
```  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.   
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 <span data-ttu-id="ee36d-108">O `GetProcesses` operação é anotada com a <xref:System.ServiceModel.Web.WebGetAttribute> atributo que permite que você controle como [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] envia solicitações HTTP GET para operações de serviço e especificar o formato das mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="ee36d-108">The `GetProcesses` operation is annotated with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute that enables you to control how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dispatches HTTP GET requests to service operations and specify the format of the messages sent.</span></span>  
  
 <span data-ttu-id="ee36d-109">Como qualquer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviço, feeds de agregação podem ser próprio hospedados em qualquer aplicativo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ee36d-109">Like any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, syndication feeds can be self hosted in any managed application.</span></span> <span data-ttu-id="ee36d-110">Serviços de distribuição exigem uma associação específica (o <xref:System.ServiceModel.WebHttpBinding>) e um comportamento de ponto de extremidade específico (o <xref:System.ServiceModel.Description.WebHttpBehavior>) para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="ee36d-110">Syndication services require a specific binding (the <xref:System.ServiceModel.WebHttpBinding>) and a specific endpoint behavior (the <xref:System.ServiceModel.Description.WebHttpBehavior>) to function correctly.</span></span> <span data-ttu-id="ee36d-111">O novo <xref:System.ServiceModel.Web.WebServiceHost> classe fornece uma API conveniente para a criação de tais pontos de extremidade sem configuração específica.</span><span class="sxs-lookup"><span data-stu-id="ee36d-111">The new <xref:System.ServiceModel.Web.WebServiceHost> class provides a convenient API for creating such endpoints without specific configuration.</span></span>  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 <span data-ttu-id="ee36d-112">Como alternativa, você pode usar <xref:System.ServiceModel.Activation.WebServiceHostFactory> de dentro de um arquivo. svc hospedados no IIS para fornecer funcionalidade equivalente (essa técnica não será demonstrada neste código de exemplo).</span><span class="sxs-lookup"><span data-stu-id="ee36d-112">Alternatively, you can use <xref:System.ServiceModel.Activation.WebServiceHostFactory> from within an IIS-hosted .svc file to provide equivalent functionality (this technique is not demonstrated in this sample code).</span></span>  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 <span data-ttu-id="ee36d-113">Como este serviço recebe solicitações que usam o padrão HTTP GET, você pode usar qualquer cliente RSS ou ATOM reconhecimento para acessar o serviço.</span><span class="sxs-lookup"><span data-stu-id="ee36d-113">Because this service receives requests using the standard HTTP GET, you can use any RSS or ATOM-aware client to access the service.</span></span> <span data-ttu-id="ee36d-114">Por exemplo, você pode exibir a saída desse serviço, navegando até o feed/de diagnóstico de http://localhost:8000 /? formato = atom ou feed/de diagnóstico de http://localhost:8000 /? formato = rss em um navegador com suporte a RSS, como o Internet Explorer 7.</span><span class="sxs-lookup"><span data-stu-id="ee36d-114">For example, you can view the output of this service by navigating to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss in an RSS-aware browser such as Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="ee36d-115">Você também pode usar o [como o WCF Syndication objeto modelo mapeia para Atom e RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) para ler dados distribuídos e processá-la usando o código obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ee36d-115">You can also use the [How the WCF Syndication Object Model Maps to Atom and RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) to read syndicated data and process it using imperative code.</span></span>  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ee36d-116">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="ee36d-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ee36d-117">Verifique se você tem a permissão de registro de endereço para HTTP e HTTPS no computador, conforme explicado no conjunto de backup instruções [único procedimento de instalação para os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ee36d-117">Ensure that you have the right address registration permission for HTTP and HTTPS on the computer as explained in the set up instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ee36d-118">Compile a solução.</span><span class="sxs-lookup"><span data-stu-id="ee36d-118">Build the solution.</span></span>  
  
3.  <span data-ttu-id="ee36d-119">Execute o aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="ee36d-119">Run the console application.</span></span>  
  
4.  <span data-ttu-id="ee36d-120">Durante a execução do aplicativo de console, navegue até o feed/de diagnóstico de http://localhost:8000 /? formato = atom ou feed/de diagnóstico de http://localhost:8000 /? formato = rss usando um navegador com suporte para RSS.</span><span class="sxs-lookup"><span data-stu-id="ee36d-120">While the console application is running, navigate to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss using an RSS-aware browser.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee36d-121">Os exemplos podem mais ser instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="ee36d-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ee36d-122">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ee36d-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ee36d-123">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="ee36d-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee36d-124">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="ee36d-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a><span data-ttu-id="ee36d-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ee36d-125">See Also</span></span>  
 [<span data-ttu-id="ee36d-126">Modelo de programação WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="ee36d-126">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="ee36d-127">Sindicalização do WCF</span><span class="sxs-lookup"><span data-stu-id="ee36d-127">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)