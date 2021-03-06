---
title: Como usar blocos finally
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 213ab53c68a37ac0ba5f337a1d6fc32bfe6f8989
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190209"
---
# <a name="how-to-use-finally-blocks"></a>Como usar blocos finally

Quando ocorre uma exceção, a execução é interrompida e o controle é dado ao manipulador de exceção apropriado. Geralmente, isso significa que linhas de código que você espera que sejam executadas são ignoradas. A limpeza de alguns recursos, assim como o fechamento de um arquivo, precisará ser feita mesmo se uma exceção for gerada. Para fazer isso, você pode usar um bloco `finally`. Um bloco `finally` sempre é executado, independentemente de uma exceção ser ou não gerada.

O exemplo de código a seguir usa um bloco `try`/`catch` para capturar uma <xref:System.ArgumentOutOfRangeException>. O método `Main` cria duas matrizes e tenta copiar uma para a outra. A ação gera um <xref:System.ArgumentOutOfRangeException> e o erro é gravado no console. Este bloco `finally` é executado independentemente resultado da ação de cópia.

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a>Consulte também

- [Exceções](index.md)
