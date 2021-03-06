---
title: XAttribute 클래스 개요
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: ceafe5478e41fb4c2038fd9300ef7b1ee6cb8411
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636655"
---
# <a name="xattribute-class-overview-visual-basic"></a>XAttribute 클래스 개요 (Visual Basic)
특성은 요소와 연결된 이름/값 쌍입니다. <xref:System.Xml.Linq.XAttribute> 클래스는 XML 특성을 나타냅니다.  
  
## <a name="overview"></a>개요  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 특성 작업은 요소 작업과 유사합니다. 특성과 요소의 생성자는 유사합니다. 특성과 요소의 컬렉션을 검색하는 데 사용하는 메서드는 유사합니다. 특성 컬렉션에 대 한 LINQ 쿼리 식은 요소 컬렉션에 대 한 LINQ 쿼리 식과 매우 유사 하 게 보입니다.  
  
 특성이 요소에 추가된 순서는 유지됩니다. 즉, 특성을 반복하는 경우 특성은 추가된 동일한 순서로 표시됩니다.  
  
## <a name="the-xattribute-constructor"></a>XAttribute 생성자  
 <xref:System.Xml.Linq.XAttribute> 클래스의 다음 생성자는 가장 일반적으로 사용하는 생성자입니다.  
  
|생성자|설명|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<xref:System.Xml.Linq.XAttribute> 개체를 만듭니다. `name` 인수는 특성의 이름을 지정하고, `content`는 특성의 내용을 지정합니다.|  
  
### <a name="creating-an-element-with-an-attribute"></a>특성을 사용하여 요소 만들기  
 다음 코드는 Visual Basic에서 XML 리터럴을 사용 하는 특성이 포함 된 요소를 보여 줍니다.  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>특성의 함수 생성  
 <xref:System.Xml.Linq.XAttribute> 개체의 생성과 함께 다음과 같이 <xref:System.Xml.Linq.XElement> 개체를 인라인으로 생성할 수 있습니다.  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>특성은 노드가 아님  
 특성과 요소 사이에는 차이점이 있습니다. <xref:System.Xml.Linq.XAttribute> 개체는 XML 트리의 노드가 아닙니다. 특성은 XML 요소와 연결된 이름/값 쌍입니다. DOM(문서 개체 모델)과 대조적으로 이는 XML의 구조를 더욱 충실하게 반영합니다. <xref:System.Xml.Linq.XAttribute> 개체가 실제로 XML 트리의 노드는 아니지만 <xref:System.Xml.Linq.XAttribute> 개체 작업은 <xref:System.Xml.Linq.XElement> 개체 작업과 매우 유사합니다.  
  
 이 차이는 주로 노드 수준에서 XML 트리 작업을 하는 코드를 작성하는 개발자에게만 중요합니다. 대부분의 개발자는 이 차이에 대해 염려하지 않습니다.  
  
## <a name="see-also"></a>참조

- [LINQ to XML 프로그래밍 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
