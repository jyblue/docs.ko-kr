---
title: ICorDebugRegisterSet::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792086"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext 메서드
현재 스레드의 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `contextSize`  
 진행 `context` 배열의 크기 (바이트)입니다.  
  
 `context`  
 [in, out] 현재 플랫폼에 대 한 Win32 `CONTEXT` 구조를 구성 하는 바이트 배열입니다.  
  
## <a name="remarks"></a>주의  
 스레드가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 `GetThreadContext` 함수 대신이 함수를 호출 해야 합니다. 반환 되는 데이터는 현재 플랫폼에 대 한 Win32 `CONTEXT` 구조입니다.  
  
 리프가 아닌 프레임의 경우 클라이언트는 [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)를 사용 하 여 유효한 레지스터를 확인 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
