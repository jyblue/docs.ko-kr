---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: a8a377074ca1005ad8089dfd8e2a6a464bb86f60
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791362"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a>ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드

현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a>매개 변수

`ppNotificationObject`\
제한이 현재 스레드의 현재 `ICorDebugManagedCallback3::CustomNotification` 개체에 대 한 포인터입니다.

## <a name="remarks"></a>주의

`ICorDebugManagedCallback3::CustomNotification` 콜백 내에서 메서드가 호출 되지 않거나 현재 알림 개체가 없는 경우 `ppNotificationObject` 값은 null입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>참조

- [ICorDebugThread4 인터페이스](icordebugthread4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
