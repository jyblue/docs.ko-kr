---
title: ICorDebugProcess6 인터페이스
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: 73ef1a64deaf5420246fc1ab3e9f88ba5bf049a5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792227"
---
# <a name="icordebugprocess6-interface"></a>ICorDebugProcess6 인터페이스
네이티브 예외 디버그 이벤트에서 인코딩되는 관리되는 디버그 이벤트 디코딩, 가상 모듈 분할 등의 기능을 사용할 수 있도록 ICorDebugProcess 인터페이스를 논리적으로 확장합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[DecodeEvent 메서드](icordebugprocess6-decodeevent-method.md)|특수하게 작성된 네이티브 예외 디버그 이벤트의 페이로드에서 캡슐화된 관리되는 디버그 이벤트를 디코딩합니다.|  
|[EnableVirtualModuleSplitting 메서드](icordebugprocess6-enablevirtualmodulesplitting-method.md)|가상 모듈 분할을 사용하거나 사용하지 않도록 설정합니다.|  
|[GetCode 메서드](icordebugprocess6-getcode-method.md)|특정 코드 주소에서 관리 코드에 대한 정보를 가져옵니다.|  
|[GetExportStepInfo 메서드](icordebugprocess6-getexportstepinfo-method.md)|관리 코드를 단계별로 실행할 수 있도록 런타임에 내보낸 함수에 대한 정보를 제공합니다.|  
|[MarkDebuggerAttached 메서드](icordebugprocess6-markdebuggerattached-method.md)|.NET Framework 클래스 라이브러리의 <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> 메서드가 `true`를 반환하도록 디버기의 내부 상태를 변경합니다.|  
|[ProcessStateChanged 메서드](icordebugprocess6-processstatechanged-method.md)|프로세스가 실행 중임을 [ICorDebug](icordebug-interface.md) 에 알립니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다. .NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
