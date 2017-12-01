---
title: Interface ICorDebugNativeFrame2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2
helpviewer_keywords: ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c33eaa36313f0cf6aae904761fb40bb2dbf9d753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="c97d2-102">Interface ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="c97d2-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="c97d2-103">Fornece métodos que testam relações de quadros pai e filho.</span><span class="sxs-lookup"><span data-stu-id="c97d2-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c97d2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c97d2-104">Methods</span></span>  
  
|<span data-ttu-id="c97d2-105">Método</span><span class="sxs-lookup"><span data-stu-id="c97d2-105">Method</span></span>|<span data-ttu-id="c97d2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c97d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c97d2-107">Método IsChild</span><span class="sxs-lookup"><span data-stu-id="c97d2-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="c97d2-108">Determina se o quadro atual é um quadro filho.</span><span class="sxs-lookup"><span data-stu-id="c97d2-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="c97d2-109">Método IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="c97d2-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="c97d2-110">Determina se o intervalo especificado é o pai do quadro atual.</span><span class="sxs-lookup"><span data-stu-id="c97d2-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="c97d2-111">Método GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="c97d2-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="c97d2-112">Retorna o tamanho cumulativo dos parâmetros na pilha em sistemas operacionais x86.</span><span class="sxs-lookup"><span data-stu-id="c97d2-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c97d2-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="c97d2-113">Remarks</span></span>  
 <span data-ttu-id="c97d2-114">Essa interface logicamente estende a interface de "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="c97d2-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c97d2-115">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="c97d2-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c97d2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c97d2-116">Requirements</span></span>  
 <span data-ttu-id="c97d2-117">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c97d2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c97d2-118">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c97d2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c97d2-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c97d2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c97d2-120">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c97d2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97d2-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c97d2-121">See Also</span></span>  
    
 [<span data-ttu-id="c97d2-122">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="c97d2-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c97d2-123">Depuração</span><span class="sxs-lookup"><span data-stu-id="c97d2-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)