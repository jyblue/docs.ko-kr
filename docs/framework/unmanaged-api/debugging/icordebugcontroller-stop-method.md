---
title: ICorDebugController::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: 3a107176e48a88a0a04534f7044c1e416caf4091
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788889"
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop 메서드
프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwTimeoutIgnored`  
 사용되지 않습니다.  
  
## <a name="remarks"></a>주의  
 `Stop` 프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다. 관리 전용 디버깅 세션 중에는 관리 되지 않는 스레드가 계속 실행 될 수 있지만 관리 코드를 호출 하려고 하면 차단 됩니다. Interop 디버깅 세션 중에는 관리 되지 않는 스레드도 중지 됩니다. `dwTimeoutIgnored` 값은 현재 무시 되 고 무한 (-1)으로 처리 됩니다. 교착 상태가 발생 하 여 협조적 중지가 실패 하면 모든 스레드가 일시 중단 되 고 E_TIMEOUT 반환 됩니다.  
  
> [!NOTE]
> `Stop`는 디버깅 API의 유일한 동기 메서드입니다. `Stop`에서 S_OK 반환 하는 경우 프로세스가 중지 됩니다. 수신기에 중지를 알리기 위한 콜백이 제공 되지 않습니다. 디버거는 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 를 호출 하 여 프로세스를 다시 시작할 수 있도록 해야 합니다.  
  
 디버거는 중지 카운터를 유지 관리 합니다. 카운터가 0으로 이동 하면 컨트롤러가 다시 시작 됩니다. `Stop` 또는 디스패치 된 각 콜백을 호출할 때마다 카운터가 증가 합니다. `ICorDebugController::Continue`에 대 한 각 호출은 카운터를 감소 시킵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
