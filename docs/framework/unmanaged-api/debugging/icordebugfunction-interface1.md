---
title: ICorDebugFunction 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: ba0e0b1b2bac785e28f41e09dda74841121a748d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794511"
---
# <a name="icordebugfunction-interface"></a>ICorDebugFunction 인터페이스

관리되는 함수 또는 메서드를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](icordebugfunction-createbreakpoint-method.md)|이 함수의 시작 부분에 중단점을 만듭니다.|  
|[GetClass 메서드](icordebugfunction-getclass-method.md)|이 함수가 멤버인 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.|  
|[GetCurrentVersionNumber 메서드](icordebugfunction-getcurrentversionnumber-method.md)|이 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.|  
|[GetILCode 메서드](icordebugfunction-getilcode-method.md)|이 함수의 MSIL (Microsoft 중간 언어) 코드를 가져옵니다.|  
|[GetLocalVarSigToken 메서드](icordebugfunction-getlocalvarsigtoken-method.md)|이 `ICorDebugFunction` 인스턴스가 나타내는 함수의 지역 변수 서명에 대 한 메타 데이터 토큰을 가져옵니다.|  
|[GetModule 메서드](icordebugfunction-getmodule-method.md)|이 함수가 정의 된 모듈을 가져옵니다.|  
|[GetNativeCode 메서드](icordebugfunction-getnativecode-method.md)|이 함수에 대 한 네이티브 코드를 가져옵니다.|  
|[GetToken 메서드](icordebugfunction-gettoken-method.md)|이 함수에 대 한 메타 데이터 토큰을 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 `ICorDebugFunction` 인터페이스가 제네릭 형식 매개 변수가 있는 함수를 나타내지 않습니다. 예를 들어 `ICorDebugFunction` 인스턴스는 `Func<T>`를 나타내지만 `Func<string>`되지 않습니다. [ICorDebugILFrame2:: Enumerat 매개 변수](icordebugilframe2-enumeratetypeparameters-method.md) 를 호출 하 여 제네릭 형식 매개 변수를 가져옵니다.  
  
 메서드의 메타 데이터 토큰, `mdMethodDef`및 메서드의 `ICorDebugFunction` 개체 간 관계는 함수에서 편집 하며 계속 하기가 허용 되는지 여부에 따라 달라 집니다.  
  
- 함수에서 편집 하며 계속 하기를 사용할 수 없는 경우 `ICorDebugFunction` 개체와 `mdMethodDef` 토큰 사이에 일 대 일 관계가 있습니다. 즉,이 함수에는 하나의 `ICorDebugFunction` 개체와 하나의 `mdMethodDef` 토큰이 있습니다.  
  
- 함수에서 편집 하며 계속 하기를 사용할 수 있는 경우 `ICorDebugFunction` 개체와 `mdMethodDef` 토큰 사이에 다 대 일 관계가 있습니다. 즉, 함수에는 함수의 각 버전에 대 한 `ICorDebugFunction`의 여러 인스턴스가 포함 될 수 있지만 하나의 `mdMethodDef` 토큰만 있을 수 있습니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:**  CorGuids .lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
