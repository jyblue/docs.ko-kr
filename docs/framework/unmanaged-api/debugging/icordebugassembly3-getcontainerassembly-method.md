---
title: ICorDebugAssembly3::GetContainerAssembly 메서드
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 969cca6d5613670fc4b26fc973785b4874c3684c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778066"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>ICorDebugAssembly3::GetContainerAssembly 메서드
이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppAssembly`  
 컨테이너 어셈블리를 나타내는 ICorDebugAssembly 개체의 주소에 대 한 포인터 이거나, 메서드 호출이 실패할 경우 **null** 입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드 호출이 성공 하면이 고, 그렇지 않으면 `S_OK`입니다. 그렇지 않으면 `S_FALSE`및 `ppAssembly`가 **null**입니다.  
  
## <a name="remarks"></a>주의  
 이 어셈블리를 단일 컨테이너 어셈블리 내의 다른 어셈블리와 병합한 경우 이 메서드는 컨테이너 어셈블리를 반환합니다. 자세한 내용과 용어에 대 한 자세한 내용은 [ICorDebugProcess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) 항목을 참조 하세요.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugAssembly3 인터페이스](icordebugassembly3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
