---
title: 기타 제어 구조
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348127"
---
# <a name="other-control-structures-visual-basic"></a>기타 제어 구조(Visual Basic)
Visual Basic는 리소스를 삭제 하거나 개체 참조를 반복 해야 하는 횟수를 줄이는 데 도움이 되는 제어 구조를 제공 합니다.  
  
## <a name="usingend-using-construction"></a>Using ... 생성 사용 종료  
 `Using...End Using` 생성은 SQL 연결과 같은 리소스를 사용 하는 문 블록을 설정 합니다. 필요에 따라 `Using` 문을 사용 하 여 리소스를 가져올 수 있습니다. `Using` 블록을 종료 하면 Visual Basic 다른 코드에서 사용할 수 있도록 리소스를 자동으로 삭제 합니다. 리소스는 로컬 이며 삭제 가능 해야 합니다. 자세한 내용은 [using 문](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.  
  
## <a name="withend-with-construction"></a>... 생성으로 종료  
 `With...End With` 생성을 사용 하면 개체 참조를 한 번 지정한 다음 해당 멤버에 액세스 하는 일련의 문을 실행할 수 있습니다. 이를 통해 Visual Basic는 코드를 단순화 하 고 성능을 향상 시킬 수 있습니다 .이를 통해 액세스 하는 각 문에 대 한 참조를 다시 설정할 필요가 없기 때문입니다. 자세한 내용은 다음 [을 참조 하세요. End With 문](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)  
  
## <a name="see-also"></a>참고자료

- [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [판단 구조](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [중첩 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using 문](../../../../visual-basic/language-reference/statements/using-statement.md)
- [With...End With 문](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
