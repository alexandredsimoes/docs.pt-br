---
title: Função InheritsFrom (referência de API não gerenciada)
description: A função InheritsFrom determina se uma classe ou instância derivada de uma classe pai específico.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4784e22d5a3eec031fbee00441958a62d66b52df
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222101"
---
# <a name="inheritsfrom-function"></a>Função InheritsFrom
Determina se a classe ou instância atual é derivada de uma classe pai especificada.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxe  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a>Parâmetros

`vFunc`  
[in] Esse parâmetro é usado.

`ptr`  
[in] Um ponteiro para um [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instância.

`wszAncestor`  
[in] O nome da classe. `wszAncestor` deve apontar para um válido `LPCWSTR`.

## <a name="return-value"></a>Valor retornado

Os seguintes valores retornados por essa função são definidos na *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:

|Constante  |Valor  |Descrição  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | O objeto atual herda `wszAncestor`.  |
| `WBEM_S_FALSE` | 1 | O objeto atual não herda de `wszAncestor`. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszAncestor` é `null`. |
  
## <a name="remarks"></a>Comentários

Essa função encapsula uma chamada para o [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** confira [Requisitos do sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** WMINet_Utils.idl  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte também  
[WMI e contadores de desempenho (referência de API não gerenciada)](index.md)
