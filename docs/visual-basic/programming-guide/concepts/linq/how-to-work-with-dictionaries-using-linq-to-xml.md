---
title: '작업: LINQ to XML을 사용할 때 사전 작업'
ms.date: 07/20/2015
ms.assetid: 6cb3f969-1986-414a-b850-87418712edea
ms.openlocfilehash: 12327be3c9d32d34866691b156f58fd1e8e40240
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332360"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-visual-basic"></a>방법: LINQ to XML를 사용 하 여 사전 작업 (Visual Basic)
다양한 데이터 구조를 XML로 변환하고 XML을 다시 다른 데이터 구조로 변환하는 것이 편리한 경우가 많습니다. 이 항목에서는 <xref:System.Collections.Generic.Dictionary%602>를 XML로 변환하고 다시 그 반대로 변환하여 이 일반적인 방법을 구체적으로 구현하는 것을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예에서는 포함 된 식에서 XML 리터럴과 쿼리를 사용 합니다. 이 쿼리는 새 <xref:System.Xml.Linq.XElement> 개체를 프로젝션 합니다. 그러면 `Root` <xref:System.Xml.Linq.XElement> 개체에 대 한 새 내용이 됩니다.  
  
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
  
 이 코드의 결과는 다음과 같습니다.  
  
```xml  
          <Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a>예제  
 다음 코드에서는 XML에서 사전을 만듭니다.  
  
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
  
 이 코드의 결과는 다음과 같습니다.  
  
```console  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a>참고 항목

- [프로젝션 및 변환 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
