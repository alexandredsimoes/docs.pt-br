---
title: '&lt;mensagem&gt; de &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 65a8b0fa120d23931ad218ac67846c066b050af8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515808"
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a>&lt;mensagem&gt; de &lt;netMsmqBinding&gt;
Define as configurações de segurança de mensagem SOAP sobre isso `netMsmqBinding` associação.  
  
 \<system.ServiceModel>  
\<associações >  
\<netMsmqBinding>  
\<associação >  
\<segurança >  
\<message>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|algorithmSuite|Define a mensagem de algoritmos de criptografia e encapsulamento de chave que são usados para fins de segurança baseada em mensagens para mensagens enviadas pelo transporte MSMQ.<br /><br /> O valor padrão é `Aes256`. Esse atributo é do tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|clientCredentialType|Especifica o tipo de credencial a ser usada ao executar a autenticação de cliente para mensagens enviadas por meio do transporte MSMQ. Os valores válidos incluem o seguinte:<br /><br /> -None: Isso permite que o serviço interaja com clientes anônimos. Nem o serviço nem o cliente requer uma credencial.<br />-Windows: Isso permite que as trocas SOAP estar sob o contexto autenticado de uma credencial do Windows. Isso sempre executa a autenticação Kerberos.<br />-Nome de usuário: Isso permite que o serviço exigir que o cliente seja autenticado usando uma credencial de nome de usuário. A credencial nesse caso, deve ser especificado usando o `clientCredentials` comportamento **cuidado:** Windows Communication Foundation (WCF) não oferece suporte para enviar uma senha digest ou derivação de chaves usando a senha e usando essas chaves para segurança de mensagem. Portanto, o WCF impõe que o exchange esteja protegido ao usar as credenciais de nome de usuário. Esse modo exige que o certificado de serviço seja especificado no lado cliente usando `clientCredential` comportamento e `serviceCertificate`. <br /><br /> -Certificate: Isso permite que o serviço exigir que o cliente seja autenticado usando um certificado. A credencial do cliente nesse caso, deve ser especificado usando o `clientCredentials` comportamento. A credencial de serviço neste caso deve ser especificado usando o `clientCredentials` comportamento especificando o `serviceCertificate`.<br />-CardSpace: Isso permite que o serviço exigir que o cliente seja autenticado usando um CardSpace. O `serviceCertiifcate` devem ser provisionados no `clientCredential` comportamento.<br /><br /> O valor padrão é `Windows`. Esse atributo é do tipo <xref:System.ServiceModel.MessageCredentialType>.|  
  
### <a name="child-elements"></a>Elementos filho  
 Nenhum  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Define as configurações de segurança para uma associação.|  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [Filas no WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Protegendo serviços e clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associações](../../../../../docs/framework/wcf/bindings.md)  
 [Configurando associações fornecidas pelo sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Usando associações para configurar clientes e serviços do Windows Communication Foundation](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<associação >](../../../../../docs/framework/misc/binding.md)
