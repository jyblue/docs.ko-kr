---
title: ICorDebugFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: ba138e79e0d6fb6f9c5e9c3efe3466f3c88cccae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782617"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame 인터페이스

현재 스택의 프레임을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateStepper 메서드](icordebugframe-createstepper-method.md)|이 `ICorDebugFrame`에 상대적인 단계별 작업을 수행할 ICorDebugStepper를 가져옵니다.|  
|[GetCallee 메서드](icordebugframe-getcallee-method.md)|이 프레임에서 호출한 현재 체인의 `ICorDebugFrame`에 대 한 포인터를 가져오거나, 체인에서 가장 안쪽 프레임 인 경우 null을 반환 합니다.|  
|[GetCaller 메서드](icordebugframe-getcaller-method.md)|이 프레임을 호출한 현재 체인의 `ICorDebugFrame`에 대 한 포인터를 가져오거나, 체인에서 가장 바깥쪽 프레임 인 경우 null을 반환 합니다.|  
|[GetChain 메서드](icordebugframe-getchain-method.md)|이 `ICorDebugFrame` 포함 된 ICorDebugChain에 대 한 포인터를 가져옵니다.|  
|[GetCode 메서드](icordebugframe-getcode-method.md)|이 스택 프레임과 연결 된 ICorDebugCode에 대 한 포인터를 가져옵니다.|  
|[GetFunction 메서드](icordebugframe-getfunction-method.md)|이 스택 프레임과 연결 된 코드를 포함 하는 ICorDebugFunction에 대 한 포인터를 가져옵니다.|  
|[GetFunctionToken 메서드](icordebugframe-getfunctiontoken-method.md)|이 스택 프레임과 연결 된 코드를 포함 하는 함수에 대 한 메타 데이터 토큰을 가져옵니다.|  
|[GetStackRange 메서드](icordebugframe-getstackrange-method.md)|이 `ICorDebugFrame`표시 하는 스택 프레임의 절대 주소 범위를 가져옵니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
