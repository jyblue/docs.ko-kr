---
title: ICorDebugInstanceFieldSymbol::GetOffset 메서드
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: f7c13d397b39698bdf1a22f14820680e1fd0a25f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782296"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a>ICorDebugInstanceFieldSymbol::GetOffset 메서드
부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pcbOffset`  
 부모 클래스에서 이 인스턴스 필드가 오프셋되는 바이트 수에 대한 포인터입니다.  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugInstanceFieldSymbol 인터페이스](icordebuginstancefieldsymbol-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
