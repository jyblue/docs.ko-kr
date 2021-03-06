---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: afeec3df03fc2b122ca8deb8123b79314b5e3837
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782429"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a>ICorDebugILFrame4::EnumerateLocalVariablesEx 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 프레임의 로컬 변수에 대한 열거자를 가져오고 필요에 따라 프로파일러 ReJIT 계측에 추가된 변수를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `flags`  
 진행 프로파일러 ReJIT 계측에 추가 된 변수가 프레임에 포함 되는지 여부를 지정 하는 [Ilcodekind](ilcodekind-enumeration.md) 열거형 멤버입니다.  
  
 `ppValueEnum`  
 제한이 이 프레임에 있는 지역 변수의 열거자 인 "ICorDebugValueEnum" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드는 선택적으로 profiler ReJIT 계측에 추가 된 변수에 액세스 한다는 점을 제외 하 고 [Enumeratelocalvariables](icordebugilframe-enumeratelocalvariables-method.md) 메서드와 비슷합니다. `ILCODE_ORIGINAL_IL` `flags`를 설정 하는 것은 [ICorDebugILFrame:: EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)를 호출 하는 것과 같습니다. `flags`을 `ILCODE_REJIT_IL`로 설정하면 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다. IL(중간 언어)이 계측되지 않는 경우 열거형은 비어 있으며 메서드는 `S_OK`를 반환합니다.  
  
 열거자는 실행 중인 메서드의 모든 로컬 변수를 포함하지 않을 수 있습니다. 이러한 변수 중 일부는 활성 상태가 아닐 수 있기 때문입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugILFrame4 인터페이스](icordebugilframe4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [ReJIT: 방법 가이드](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
