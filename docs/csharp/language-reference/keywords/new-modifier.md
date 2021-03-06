---
title: Modificador new (referência em C#)
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 496339a7c3b95f16fd13479b096d90058b0799d4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213534"
---
# <a name="new-modifier-c-reference"></a>Modificador new (referência em C#)

Quando usada como um modificador de declaração, a palavra-chave `new` oculta explicitamente um membro herdado de uma classe base. Quando você oculta um membro herdado, a versão derivada do membro substitui a versão da classe base. Embora possa ocultar membros sem usar o modificador `new`, você obtém um aviso do compilador. Se você usar `new` para ocultar explicitamente um membro, ele suprime o aviso.

Para ocultar um membro herdado, declare-o na classe derivada usando o mesmo nome de membro e modifique-o com a palavra-chave `new`. Por exemplo:

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

Neste exemplo, `BaseC.Invoke` é ocultado por `DerivedC.Invoke`. O campo `x` não é afetado porque não é ocultado por um nome semelhante.

A ocultação de nome por meio da herança assume uma das seguintes formas:

Normalmente, uma constante, campo, propriedade ou tipo que é apresentado em uma classe ou struct oculta todos os membros da classe base que compartilham seu nome.  Há casos especiais.  Por exemplo, se você declarar que um novo campo com o nome `N` tem um tipo que não pode ser invocado e um tipo base declarar que `N` é um método, o novo campo não ocultará a declaração base na sintaxe de invocação.  Consulte a [Especificação da linguagem C# 5.0](https://www.microsoft.com/download/details.aspx?id=7029) para obter detalhes (consulte a seção "Pesquisa de membro" na seção "Expressões").

Um método introduzido em uma classe ou struct oculta propriedades, campos e tipos que compartilham esse nome na classe base. Ele também oculta todos os métodos da classe base que têm a mesma assinatura.

Um indexador introduzido em uma classe ou struct oculta todos os indexadores de classe base que têm a mesma assinatura.

É um erro usar `new` e [override](override.md) no mesmo membro, porque os dois modificadores têm significados mutuamente exclusivos. O modificador `new` cria um novo membro com o mesmo nome e faz com que o membro original seja ocultado. O modificador `override` estende a implementação de um membro herdado.

Usar o modificador `new` em uma declaração que não oculta um membro herdado gera um aviso.

## <a name="example"></a>Exemplo

Neste exemplo, uma classe base, `BaseC` e uma classe derivada, `DerivedC`, usam o mesmo nome do campo `x`, que oculta o valor do campo herdado. O exemplo demonstra o uso do modificador `new`. Ele também demonstra como acessar os membros ocultos da classe base usando seus nomes totalmente qualificados.

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a>Exemplo

Neste exemplo, uma classe aninhada oculta uma classe que tem o mesmo nome na classe base. O exemplo demonstra como usar o modificador `new` para eliminar a mensagem de aviso e como acessar os membros da classe oculta usando seus nomes totalmente qualificados.

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

Se você remover o modificador `new`, o programa ainda será compilado e executado, mas você receberá o seguinte aviso:

```
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a>especificação da linguagem C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Consulte também

- [Referência de C#](../../language-reference/index.md)
- [Guia de Programação em C#](../../programming-guide/index.md)
- [Palavras-chave do C#](index.md)
- [Palavras-chave do operador](operator-keywords.md)
- [Modificadores](modifiers.md)
- [Controle de versão com as palavras-chave override e new](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [Quando usar as palavras-chave override e new](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
