---
title: ICorProfilerInfo3::RequestProfilerDetach 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.RequestProfilerDetach Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type:
- apiref
ms.openlocfilehash: 8520f5fc0a6ff7e71f40cd7fbb1caf68aab63197
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868514"
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>ICorProfilerInfo3::RequestProfilerDetach 메서드
런타임에 프로파일러를 분리하도록 지시합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwExpectedCompletionMilliseconds`  
 [in] 프로파일러를 언로드하기에 안전한지를 확인하기 전에 CLR(공용 언어 런타임)이 대기해야 하는 시간(밀리초)입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|분리 요청이 유효하고 분리 절차는 다른 스레드에서 계속 진행됩니다. 분리가 완료되면 `ProfilerDetachSucceeded` 이벤트가 발생합니다.|  
|E_ CORPROF_E_CALLBACK3_REQUIRED|프로파일러가 분리 작업을 지원 하기 위해 구현 해야 하는 [ICorProfilerCallback3](icorprofilercallback3-interface.md) 인터페이스에 대 한 [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) 시도에 실패 했습니다. 분리가 시도되지 않았습니다.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|프로파일러가 시작 시 변경할 수 없는 플래그를 설정하므로 분리가 불가능합니다. 분리가 시도되지 않았고 프로파일러가 완전히 연결됩니다.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|프로파일러가 계측 된 MSIL (Microsoft 중간 언어) 코드를 사용 하거나 `leave` 후크에 /`enter`삽입 했기 때문에 분리이 불가능 합니다. 분리가 시도되지 않았고 프로파일러가 완전히 연결됩니다.<br /><br /> **참고** 계측 된 MSIL은 [Setilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md) 메서드를 사용 하 여 프로파일러에서 제공 하는 코드입니다.|  
|CORPROF_E_RUNTIME_UNINITIALIZED|관리되는 애플리케이션에서 런타임이 아직 초기화되지 않았습니다. 즉, 런타임이 완전히 로드 되지 않았습니다. 이 오류 코드는 프로파일러 콜백의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 메서드 내에서 분리가 요청 될 때 반환 될 수 있습니다.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|지원되지 않는 시간에 `RequestProfilerDetach`가 호출되었습니다. 이는 가비지 수집을 허용할 수 없는 [ICorProfilerCallback](icorprofilercallback-interface.md) [메서드 내](icorprofilercallback-interface.md) 에서 또는 관리 되는 스레드에서 메서드가 호출 되지 않는 경우에 발생 합니다. 자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md)를 참조 하세요.|  
  
## <a name="remarks"></a>주의  
 분리 절차 중에 분리 스레드(프로파일러 분리를 위해 특별히 만들어진 스레드)는 가끔 모든 스레드가 프로파일러 코드를 종료했는지를 확인합니다. 프로파일러는 `dwExpectedCompletionMilliseconds` 매개 변수를 통해 소요 시간 예상 값을 제공해야 합니다. 프로파일러가 특정 `ICorProfilerCallback*` 메서드 내에서 사용하는 일반적인 시간을 값으로 사용하는 것이 좋습니다. 이 값은 프로파일러의 최대 소요 예상 시간의 절반 이상이어야 합니다.  
  
 분리 스레드에서는 `dwExpectedCompletionMilliseconds`를 사용하여 프로파일러 콜백 코드가 스택에서 모두 제거되었는지를 확인하기 전의 대기 기간을 결정합니다. 다음 알고리즘의 세부 정보는 CLR의 미래 릴리스에 변경될 수 있지만 프로파일러를 안전하게 언로드할 수 있는 시점을 결정할 때 `dwExpectedCompletionMilliseconds`를 사용할 수 있는 한 가지 방법을 보여 줍니다. 분리 스레드는 먼저 `dwExpectedCompletionMilliseconds`밀리초 동안 대기합니다. 활성화가 중지 된 후에 CLR에서 프로파일러 콜백 코드가 아직 있다는 것을 알게 되 면 분리 스레드는 다시 대기 하 게 됩니다. 이번에는 두 시간 (밀리초)을 `dwExpectedCompletionMilliseconds` 합니다. 이 두 번째 대기에서 활성화된 후 분리 스레드는 프로파일러 콜백 코드가 아직 있다는 것을 확인하면 다시 확인하기 전에 10분 동안 대기합니다. 분리 스레드는 10분마다 계속 다시 확인합니다.  
  
 프로파일러가 `dwExpectedCompletionMilliseconds`를 0(영)으로 지정하면 CLR은 5초 후, 다시 10초 후, 이후 10분마다 확인을 수행할 것임을 의미하는 기본값 5000을 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo3 인터페이스](icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
