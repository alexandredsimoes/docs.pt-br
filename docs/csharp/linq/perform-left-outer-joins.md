---
title: Executar junções externas esquerdas (LINQ em C#)
description: Saiba como executar junções externas esquerdas usando o LINQ em C#.
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 329fe9e17640931c5eb39b33b791a7a77a6f7b89
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506590"
---
# <a name="perform-left-outer-joins"></a>Executar junções externas esquerdas

Uma junção externa esquerda é uma junção em que cada elemento da primeira coleção é retornado, mesmo que ele tenha elementos correlacionados na segunda coleção. É possível usar o LINQ para executar uma junção externa esquerda chamando o método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nos resultados de uma junção de grupo.

## <a name="example"></a>Exemplo

O exemplo a seguir demonstra como usar o método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nos resultados de uma junção de grupo para executar uma junção externa esquerda.

A primeira etapa da produção de uma junção externa esquerda de duas coleções é executar uma junção interna usando uma junção de grupo. (Consulte [Executar junções internas](perform-inner-joins.md) para obter uma explicação desse processo.) Neste exemplo, a lista de objetos `Person` é associada internamente à lista de objetos `Pet` com base em um objeto `Person` correspondente a `Pet.Owner`.

A segunda etapa é incluir cada elemento da primeira coleção (esquerda) no conjunto de resultados, mesmo que esse elemento não tenha nenhuma correspondência na coleção direita. Isso é feito chamando <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> em cada sequência de elementos correspondentes da junção de grupo. Neste exemplo, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> é chamado em cada sequência de objetos `Pet` correspondentes. O método retorna uma coleção que contém um valor padrão único se a sequência de objetos `Pet` correspondentes estiver vazia para qualquer objeto `Person`, garantindo assim que cada objeto `Person` seja representado no conjunto de resultados.

> [!NOTE]
> O valor padrão para um tipo de referência é `null`; portanto, o exemplo procura uma referência nula antes de acessar cada elemento de cada coleção `Pet`.

[!code-csharp[CsLINQProgJoining#7](~/samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]

## <a name="see-also"></a>Consulte também

- <xref:System.Linq.Enumerable.Join%2A>  
- <xref:System.Linq.Enumerable.GroupJoin%2A>  
- [Executar junções internas](perform-inner-joins.md)  
- [Executar junções agrupadas](perform-grouped-joins.md)  
- [Tipos anônimos](../programming-guide/classes-and-structs/anonymous-types.md)  