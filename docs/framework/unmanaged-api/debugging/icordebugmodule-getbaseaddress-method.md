---
title: "Método ICorDebugModule::GetBaseAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetBaseAddress
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3e6a613fc272dc20089856b479b62afd5bf2487
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetbaseaddress-method"></a>Método ICorDebugModule::GetBaseAddress
Obtém o endereço base do módulo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pAddress`  
 [out] Um `CORDB_ADDRESS` que especifica o endereço base do módulo.  
  
## <a name="remarks"></a>Comentários  
 Se o módulo for uma nativa da imagem (ou seja, se o módulo foi produzido pelo gerador de imagem nativa, NGen.exe), seu endereço base será zero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
    
 