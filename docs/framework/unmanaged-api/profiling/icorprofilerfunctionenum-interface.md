---
title: Interface ICorProfilerFunctionEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum
helpviewer_keywords: ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1067fa6738b23492b3a58500b4cb6ba1d030304f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="1f967-102">Interface ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="1f967-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="1f967-103">Fornece métodos para iterar em sequência por meio de uma coleção de funções no common language runtime.</span><span class="sxs-lookup"><span data-stu-id="1f967-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f967-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1f967-104">Methods</span></span>  
  
|<span data-ttu-id="1f967-105">Método</span><span class="sxs-lookup"><span data-stu-id="1f967-105">Method</span></span>|<span data-ttu-id="1f967-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f967-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f967-107">Método clone</span><span class="sxs-lookup"><span data-stu-id="1f967-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="1f967-108">Obtém um ponteiro de interface para uma cópia deste `ICorProfilerFunctionEnum` interface.</span><span class="sxs-lookup"><span data-stu-id="1f967-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="1f967-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="1f967-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="1f967-110">Obtém o número de funções que foram carregados pelo aplicativo ou à força pelo criador de perfil.</span><span class="sxs-lookup"><span data-stu-id="1f967-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="1f967-111">Próximo método</span><span class="sxs-lookup"><span data-stu-id="1f967-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="1f967-112">Obtém o número especificado de funções de contíguas de uma coleção sequencial de funções, começando na posição atual do enumerador na sequência.</span><span class="sxs-lookup"><span data-stu-id="1f967-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="1f967-113">Método Reset</span><span class="sxs-lookup"><span data-stu-id="1f967-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="1f967-114">Move o cursor do enumerador para a posição inicial da sequência de.</span><span class="sxs-lookup"><span data-stu-id="1f967-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="1f967-115">Método Skip</span><span class="sxs-lookup"><span data-stu-id="1f967-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="1f967-116">Avança o cursor do enumerador de sua posição atual para que o número especificado de elementos será ignorado.</span><span class="sxs-lookup"><span data-stu-id="1f967-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f967-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="1f967-117">Remarks</span></span>  
 <span data-ttu-id="1f967-118">O `ICorProfilerFunctionEnum` interface é um enumerador.</span><span class="sxs-lookup"><span data-stu-id="1f967-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="1f967-119">Ele permite que o destinatário de uma matriz para elementos de pull do remetente a uma taxa que é apropriado para o receptor.</span><span class="sxs-lookup"><span data-stu-id="1f967-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="1f967-120">Em outras palavras, o destinatário é capaz de controlar explicitamente o fluxo de elementos da matriz, evitando, assim, os problemas associados à transmitindo matrizes grandes como parâmetros de método.</span><span class="sxs-lookup"><span data-stu-id="1f967-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="1f967-121">`ICorProfilerFunctionEnum`Enumera em funções que já tenham sido compilados JIT, mas não incluem funções que são carregadas de imagens nativas geradas com Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="1f967-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f967-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f967-122">Requirements</span></span>  
 <span data-ttu-id="1f967-123">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f967-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f967-124">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f967-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1f967-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f967-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f967-126">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f967-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f967-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f967-127">See Also</span></span>  
 [<span data-ttu-id="1f967-128">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1f967-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="1f967-129">Interfaces de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="1f967-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="1f967-130">Método EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="1f967-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)