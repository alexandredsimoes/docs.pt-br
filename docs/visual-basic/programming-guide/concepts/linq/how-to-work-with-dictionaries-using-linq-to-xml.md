---
title: 'Como: trabalhar com dicionários usando LINQ to XML (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6cb3f969-1986-414a-b850-87418712edea
ms.openlocfilehash: b6e41f61358563472f49b22df389df00e721503e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644817"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-visual-basic"></a>Como: trabalhar com dicionários usando LINQ to XML (Visual Basic)
É conveniente converter variedades de estruturas de dados para XML, e XML de volta para outras estruturas de dados. Este tópico mostra uma implementação específica dessa abordagem geral convertendo <xref:System.Collections.Generic.Dictionary%602> a XML e verso.  
  
## <a name="example"></a>Exemplo  
 Este exemplo usa literais XML e uma consulta em uma expressão inserida. Os projetos de consulta nova <xref:System.Xml.Linq.XElement> objetos, que então se tornar o novo conteúdo para o `Root` <xref:System.Xml.Linq.XElement> objeto.  
  
```vb  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)()  
dict.Add("Child1", "Value1")  
dict.Add("Child2", "Value2")  
dict.Add("Child3", "Value3")  
dict.Add("Child4", "Value4")  
Dim root As XElement = _  
    <Root>  
        <%= From keyValue In dict _  
            Select New XElement(keyValue.Key, keyValue.Value) %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 Esse código gera a seguinte saída:  
  
```xml  
          <Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a>Exemplo  
 O código a seguir cria um dicionário XML.  
  
```vb  
Dim root As XElement = _  
        <Root>  
            <Child1>Value1</Child1>  
            <Child2>Value2</Child2>  
            <Child3>Value3</Child3>  
            <Child4>Value4</Child4>  
        </Root>  
  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)  
For Each el As XElement In root.Elements  
    dict.Add(el.Name.LocalName, el.Value)  
Next  
For Each str As String In dict.Keys  
    Console.WriteLine("{0}:{1}", str, dict(str))  
Next  
```  
  
 Esse código gera a seguinte saída:  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a>Consulte também  
 [Projeções e transformações (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
