---
title: ICorDebugProcess2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: 1ef6af11851acbe0f7e9469c9432ff09f9228608
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792503"
---
# <a name="icordebugprocess2-interface"></a>ICorDebugProcess2 인터페이스
관리 코드를 실행 하는 프로세스를 나타내는 ICorDebugProcess 인터페이스의 논리적 확장입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint 메서드](icordebugprocess2-clearunmanagedbreakpoint-method.md)|`ICorDebugProcess2::SetUnmanagedBreakpoint`에 대 한 이전 호출에 의해 설정 된 지정 된 오프셋에서 중단점을 제거 합니다.|  
|[GetDesiredNGENCompilerFlags 메서드](icordebugprocess2-getdesiredngencompilerflags-method.md)|이 `ICorDebugProcess2`에서 참조 하는 프로세스에 이미지를 로드 하기 위해 CLR (공용 언어 런타임)에 대해 설정 해야 하는 플래그를 가져옵니다.|  
|[GetReferenceValueFromGCHandle 메서드](icordebugprocess2-getreferencevaluefromgchandle-method.md)|가비지 수집 핸들이 있는 지정 된 관리 되는 개체에 대 한 참조 포인터를 가져옵니다.|  
|[GetThreadForTaskID 메서드](icordebugprocess2-getthreadfortaskid-method.md)|지정 된 식별자를 가진 태스크가 실행 중인 스레드를 가져옵니다.|  
|[GetVersion 메서드](icordebugprocess2-getversion-method.md)|디버깅 중인 프로세스가 실행 되는 CLR의 버전을 가져옵니다.|  
|[SetDesiredNGENCompilerFlags 메서드](icordebugprocess2-setdesiredngencompilerflags-method.md)|JIT (just-in-time) 컴파일러가 디버깅 중인 프로세스에 이미지를 로드 하는 데 필요한 플래그를 설정 합니다.|  
|[SetUnmanagedBreakpoint 메서드](icordebugprocess2-setunmanagedbreakpoint-method.md)|지정 된 네이티브 이미지 오프셋에서 관리 되지 않는 중단점을 설정 합니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
