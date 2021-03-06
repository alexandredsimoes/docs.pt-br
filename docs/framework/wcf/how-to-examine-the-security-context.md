---
title: Como examinar o contexto de segurança
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8ff6969095a49dcae8b1d59b5b0ab28a8af24274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499470"
---
# <a name="how-to-examine-the-security-context"></a>Como examinar o contexto de segurança
Ao programar serviços Windows Communication Foundation (WCF), o contexto de segurança permite que você determine os detalhes sobre as credenciais de cliente e as declarações usadas para autenticar com o serviço. Isso é feito por meio das propriedades da <xref:System.ServiceModel.ServiceSecurityContext> classe.  
  
 Por exemplo, você pode recuperar a identidade do cliente atual usando o <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> ou <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> propriedade. Para determinar se o cliente é anônimo, use o <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> propriedade.  
  
 Você também pode determinar quais declarações estão sendo feitas em nome do cliente pela iteração através da coleção de declarações de <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> propriedade.  
  
### <a name="to-get-the-current-security-context"></a>Para obter o contexto de segurança atual  
  
-   Acessar a propriedade estática <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para obter o contexto de segurança atual. Examine as propriedades do contexto atual da referência.  
  
### <a name="to-determine-the-identity-of-the-caller"></a>Para determinar a identidade do chamador  
  
1.  Imprimir o valor de <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> e <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> propriedades.  
  
### <a name="to-parse-the-claims-of-a-caller"></a>Para analisar as declarações de um chamador  
  
1.  Retornar atuais <xref:System.IdentityModel.Policy.AuthorizationContext> classe. Use o <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> propriedade para retornar o contexto de segurança atual, em seguida, retornar o `AuthorizationContext` usando o <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> propriedade.  
  
2.  Analisar a coleção de <xref:System.IdentityModel.Claims.ClaimSet> objetos retornados pelo <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> propriedade o <xref:System.IdentityModel.Policy.AuthorizationContext> classe.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir imprime os valores da <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> e <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> propriedades de contexto de segurança atual e o <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> propriedade, o valor do recurso de declaração e o <xref:System.IdentityModel.Claims.Claim.Right%2A> propriedade de cada declaração na segurança atual contexto.  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 O código usa os namespaces a seguir:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.IdentityModel.Policy>  
  
-   <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a>Consulte também  
 [Protegendo serviços](../../../docs/framework/wcf/securing-services.md)  
 [Autenticação e identidade de serviço](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
