---
title: LINQ to XML 동적 속성 참조
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 48b51e92eb78786b2cc189e3e7daa00875b41585
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197044"
---
# <a name="linq-to-xml-dynamic-properties"></a>LINQ to XML 동적 속성

이 단원에서는 LINQ to XML의 동적 속성에 대한 참조 정보를 제공합니다. 특히 이러한 속성은 <xref:System.Xml.Linq.XAttribute> 네임스페이스에 있는 <xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq> 클래스에서 노출합니다.

[LINQ to XML을 사용한 WPF 데이터 바인딩 개요](wpf-data-binding-with-linq-to-xml-overview.md) 항목에서 설명한 대로 각 동적 속성은 동일한 클래스의 표준 공용 속성 또는 메서드와 동일합니다. 이러한 표준 멤버는 대부분의 용도에 사용되어야 하며 동적 속성은 특히 LINQ to XML 데이터 바인딩 시나리오에 제공됩니다. 이러한 클래스의 표준 멤버에 대한 자세한 내용은 <xref:System.Xml.Linq.XAttribute> 및 <xref:System.Xml.Linq.XElement> 참조 항목을 참조하세요.

이 단원의 동적 속성은 확인되는 값과 관련하여 다음 두 가지 범주로 나뉩니다.

- 단일 값으로 확인되는 `Value` 및 <xref:System.Xml.Linq.XAttribute> 클래스의 <xref:System.Xml.Linq.XElement> 속성과 같은 간단한 속성

- 인덱서 형식으로 해석되는 <xref:System.Xml.Linq.XElement>의 [Elements](elements-xelement-dynamic-property.md) 및 [Descendants](descendants-xelement-dynamic-property.md) 속성과 같은 인덱싱된 값 - 인덱서 형식을 원하는 값이나 컬렉션으로 확인하려면 확장된 이름 매개 변수가 인덱서 형식에 전달되어야 합니다.

<xref:System.Collections.Generic.IEnumerable%601> 형식의 인덱싱된 값을 반환하는 모든 동적 속성은 지연된 실행을 사용합니다. 지연된 실행에 대한 자세한 내용은 [LINQ 쿼리 소개(C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.

## <a name="reference"></a>참고

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a>참조

- [LINQ to XML로 WPF 데이터 바인딩](wpf-data-binding-with-linq-to-xml-overview.md)
- [LINQ to XML로 WPF 데이터 바인딩 개요](wpf-data-binding-with-linq-to-xml-overview.md)
- [LINQ 쿼리 소개(C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
