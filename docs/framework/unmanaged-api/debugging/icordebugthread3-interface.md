---
title: ICorDebugThread3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 19bd869aec7e4d046890d2314f5142753ba0b112
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791384"
---
# <a name="icordebugthread3-interface"></a>ICorDebugThread3 인터페이스
[ICorDebugStackWalk](icordebugstackwalk-interface.md) 및 해당 인터페이스에 대 한 진입점을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateStackWalk 메서드](icordebugthread3-createstackwalk-method.md)|스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 만듭니다.|  
|[GetActiveInternalFrames 메서드](icordebugthread3-getactiveinternalframes-method.md)|스택에서 내부 프레임 ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체)의 배열을 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 `ICorDebugThread3`는 ICorDebugThread 인터페이스에 대 한 논리적 확장입니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
