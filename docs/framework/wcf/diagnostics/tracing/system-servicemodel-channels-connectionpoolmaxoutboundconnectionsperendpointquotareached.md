---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5fa64c87bc4cd0c8dc677d8b4c59de45e31d3270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="cf898-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="cf898-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="cf898-103">O serviço de protocolo WS-AT não conseguiu se inscrever em uma transação usando o contexto de coordenação fornecido.</span><span class="sxs-lookup"><span data-stu-id="cf898-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cf898-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="cf898-104">Description</span></span>  
 <span data-ttu-id="cf898-105">Rastreada quando MSDTC não pode se inscrever em uma transação para um protocolo 2pc determinado.</span><span class="sxs-lookup"><span data-stu-id="cf898-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="cf898-106">Isso pode acontecer porque a transação não existe mais, inscrição não é mais permitido ou muitas inscrições já estão presentes.</span><span class="sxs-lookup"><span data-stu-id="cf898-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="cf898-107">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="cf898-107">Troubleshooting</span></span>  
 <span data-ttu-id="cf898-108">Verifique se a cadeia de caracteres de status dentro da mensagem de rastreamento para determinar se há qualquer item acionável.</span><span class="sxs-lookup"><span data-stu-id="cf898-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf898-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cf898-109">See Also</span></span>  
 [<span data-ttu-id="cf898-110">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="cf898-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="cf898-111">Usando o rastreamento para solucionar problemas de seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="cf898-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 <span data-ttu-id="cf898-112">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md) (Administração e diagnósticos)</span><span class="sxs-lookup"><span data-stu-id="cf898-112">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md)</span></span>