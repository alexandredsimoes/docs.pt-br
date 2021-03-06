---
title: Operador -- (Referência de C#)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 615b100447233856ab3740d075d69e3ae19285fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210423"
---
# <a name="---operator-c-reference"></a>Operador -- (Referência de C#)
O operador de decremento (`--`) decrementa o operando em 1. O operador de decremento pode aparecer antes ou depois de seu operando: `--variable` e `variable--`. A primeira forma é uma operação de decremento de prefixo. O resultado da operação será o valor do operando "depois" que ele for decrementado. A segunda forma é uma operação de decremento sufixo. O resultado da operação será o valor do operando "antes" de ser decrementado.  
  
## <a name="remarks"></a>Comentários  
 Tipos numéricos e de enumeração têm operadores de decremento predefinidos.  
  
 Os tipos definidos pelo usuário podem sobrecarregar o operador `--` (consulte [operador](../../../csharp/language-reference/keywords/operator.md)). As operações em tipos integrais geralmente são permitidas na enumeração.  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>Consulte também

- [Referência de C#](../../../csharp/language-reference/index.md)  
- [Guia de Programação em C#](../../../csharp/programming-guide/index.md)  
- [Operadores do C#](../../../csharp/language-reference/operators/index.md)
