---
title: ICorProfilerCallback6::GetAssemblyReferences 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
ms.openlocfilehash: 0717ef5fdb6c0447ceeb801f239be08f8cca5988
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865053"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a>ICorProfilerCallback6::GetAssemblyReferences 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `wszAssemblyPath`  
 [in] 메타데이터를 수정할 어셈블리의 경로와 이름입니다.  
  
 `pAsmRefProvider`  
 진행 추가할 어셈블리 참조를 지정 하는 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 인터페이스의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 콜백의 반환 값은 무시됩니다.  
  
## <a name="remarks"></a>주의  
 이 콜백은 [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출할 때 [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 설정 하 여 제어 됩니다. 프로파일러가 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백 메서드에 등록 하는 경우 런타임은 로드 될 어셈블리의 경로 및 이름과 해당 메서드에 대 한 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 인터페이스 개체에 대 한 포인터를 전달 합니다. 그러면 프로파일러는 `GetAssemblyReferences` 콜백에서 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대해 `COR_PRF_ASSEMBLY_REFERENCE_INFO` 개체를 사용 하 여 [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 메서드를 호출할 수 있습니다.  
  
 프로파일러가 어셈블리 참조를 추가하기 위해 어셈블리 메타데이터를 수정해야 하는 경우에만 `GetAssemblyReferences` 콜백을 사용합니다. 그러나 어셈블리의 메타 데이터에 대 한 실제 수정은 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)콜백 메서드에서 수행 됩니다. 프로파일러는 모듈이 로드 될 때 어셈블리 참조가 추가 된다는 것을 CLR (공용 언어 런타임)에 알리기 위해 `GetAssemblyReferences` 콜백 메서드를 구현 해야 합니다.  그러면 프로파일러가 메타데이터 어셈블리 참조를 나중에 수정하더라도 이 초기 단계에서 CLR이 결정하는 어셈블리 공유 여부가 유효하게 유지됩니다.  따라서 프로파일러 메타데이터 수정으로 인해 발생하는 `SECURITY_E_INCOMPATIBLE_SHARE` 오류 중 일부를 방지할 수 있습니다.  
  
 프로파일러에서는이 메서드에서 제공 하는 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 개체를 사용 하 여 CLR 어셈블리 참조 클로저 walker에 어셈블리 참조를 추가 합니다.  [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 개체는이 콜백 내 에서만 사용 해야 합니다. 이 콜백에서 [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 메서드를 호출 하면 수정 된 메타 데이터가 생성 되지 않지만 수정 된 어셈블리 참조 클로저 연습 에서만 수행 됩니다. 프로파일러는 `GetAssemblyReferences` 콜백을 구현 하는 경우에도 참조 어셈블리에 대 한 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 콜백 내에서 어셈블리 참조를 명시적으로 추가 하려면 여전히 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 개체를 사용 해야 합니다.  
  
 프로파일러는 동일한 어셈블리에 대해이 콜백에 대 한 중복 호출을 받을 준비를 해야 하며, 동일한 [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 호출 집합을 만들어 이러한 중복 호출에 대해 동일 하 게 응답 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback6 인터페이스](icorprofilercallback6-interface.md)
- [ModuleLoadFinished 메서드](icorprofilercallback-moduleloadfinished-method.md)
- [COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체](cor-prf-assembly-reference-info-structure.md)
- [ICorProfilerAssemblyReferenceProvider 인터페이스](icorprofilerassemblyreferenceprovider-interface.md)
