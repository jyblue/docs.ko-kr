---
title: ICorDebugILFrame::SetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
ms.openlocfilehash: 466fe421f4ff3f8983159ccb38503b75551c87bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788552"
---
# <a name="icordebugilframesetip-method"></a>ICorDebugILFrame::SetIP 메서드
MSIL (Microsoft 중간 언어) 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `nOffset`  
 MSIL 코드의 오프셋 위치입니다.  
  
## <a name="remarks"></a>주의  
 `SetIP`를 호출 하면 현재 스레드에 대 한 모든 프레임과 체인이 즉시 무효화 됩니다. `SetIP`를 호출한 후 디버거에 프레임 정보가 필요한 경우 새 스택 추적을 수행 해야 합니다.  
  
 [ICorDebug](icordebug-interface.md) 는 스택 프레임을 유효한 상태로 유지 하려고 합니다. 그러나 프레임이 유효한 상태 이더라도 초기화 되지 않은 지역 변수 같은 문제가 있을 수 있습니다. 호출자는 실행 중인 프로그램의 일관성을 보장 해야 합니다.  
  
 64 비트 플랫폼에서 명령 포인터는 `catch` 또는 `finally` 블록 밖으로 이동할 수 없습니다. `SetIP`를 호출 하 여 64 비트 플랫폼에서 이러한 이동을 수행 하는 경우 실패를 나타내는 HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
