---
title: Como especificar o tipo de credencial de cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: 5e1ff85d8a0bd45c87786f98c2cafe06472052b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499331"
---
# <a name="how-to-specify-the-client-credential-type"></a>Como especificar o tipo de credencial de cliente
Depois de definir um modo de segurança (transporte ou mensagem), você tem a opção de configuração de tipo de credencial de cliente. Essa propriedade especifica o tipo de credencial do cliente deve fornecer para o serviço de autenticação. Para obter mais informações sobre como definir o modo de segurança (uma etapa necessária antes de configurar o cliente do tipo de credencial), consulte [como: definir o modo de segurança](../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>Definir tipo de credencial de cliente em código  
  
1.  Crie uma instância da associação que o serviço usará. Este exemplo usa o <xref:System.ServiceModel.WSHttpBinding> associação.  
  
2.  Definir o <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> propriedade para um valor apropriado. Este exemplo usa o modo de mensagem.  
  
3.  Definir o <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> propriedade para um valor apropriado. Este exemplo define-o para usar a autenticação do Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>Para definir o tipo de credencial na configuração  
  
1.  Adicionar um [ \<System. ServiceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento ao arquivo de configuração.  
  
2.  Como um elemento filho, adicione um [ \<associações >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
3.  Adicione uma associação apropriado. Este exemplo usa o [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.  
  
4.  Adicionar um [ \<associação >](../../../docs/framework/misc/binding.md) elemento e defina o `name` de atributo para um valor apropriado. Este exemplo usa o nome "SecureBinding".  
  
5.  Adicionar um `<security>` associação. Definir o `mode` de atributo para um valor apropriado. Este exemplo define como `"Message"`.  
  
6.  Adicione um `<message>` ou `<transport>` elemento, conforme determinado pelo modo de segurança. Definir o `clientCredentialType` de atributo para um valor apropriado. Este exemplo usa `"Windows"`.  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Protegendo serviços](../../../docs/framework/wcf/securing-services.md)  
 [Como definir o modo de segurança](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
