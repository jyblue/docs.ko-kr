---
title: '방법: 오버로드된 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d983f5f6183c33141079ed35171f7a73f254450f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340204"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>방법: 오버로드된 프로시저 호출(Visual Basic)
프로시저 오버 로드의 이점은 호출의 유연성을 제공 합니다. 호출 하는 코드는 프로시저에 전달 하는 데 필요한 정보를 얻은 다음 전달 하는 인수에 관계 없이 단일 프로시저 이름을 호출할 수 있습니다.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>정의 된 버전이 둘 이상 있는 프로시저를 호출 하려면  
  
1. 호출 코드에서 프로시저에 전달할 데이터를 결정 합니다.  
  
2. 일반적인 방법으로 프로시저 호출을 작성 하 여 인수 목록에 데이터를 표시 합니다. 인수는 프로시저에 대해 정의 된 버전 중 하나의 매개 변수 목록과 일치 해야 합니다.  
  
3. 호출할 프로시저 버전을 결정할 필요가 없습니다. Visual Basic는 인수 목록과 일치 하는 버전으로 제어를 전달 합니다.  
  
     다음 예에서는 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)에서 선언 된 `post` 프로시저를 호출 합니다. 이 서비스는 고객 id를 가져오고 `String` 인지 아니면 `Integer`인지를 결정 한 다음 두 경우 모두 동일한 절차를 호출 합니다.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)
- [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [프로시저를 오버로드할 때 고려해야 할 사항](./considerations-in-overloading-procedures.md)
- [오버로드 확인](./overload-resolution.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
