---
title: COR_PRF_MISC 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: fe27c0fca6d38b4cff6cac2b9778cf2be68903a3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867128"
---
# <a name="cor_prf_misc-enumeration"></a>COR_PRF_MISC 열거형
특수 식별자를 지정하는 상수 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a>Members  
  
|Member|설명|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|아직 어셈블리에 연결 되지 않은 모듈에 대해 [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) 에서 사용 하는 기본 식별자입니다.|  
|`PROFILER_GLOBAL_CLASS`|클래스에 속하지 않는 전역 상수에 대 한 기본 클래스 식별자입니다.|  
|`PROFILER_GLOBAL_MODULE`|모듈에 속하지 않는 전역 개체에 대 한 기본 모듈 식별자입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
