---
title: ECustomDumpFlavor 열거형
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 057794fe524a0ee01f6f090ca7e11a4a4b523047
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124922"
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor 열거형
오류를 보고할 때 힙 덤프의 사용자 지정 하위 집합에 포함할 항목을 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|사용자 지정 힙 덤프가 미니 덤프로 시작 되 고 동일한 메서드에 전달 된 [Custom덤프 항목](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 인스턴스에 의해 지정 된 추가 데이터를 포함 하도록 지정 합니다.|  
|`DUMP_FLAVOR_NonHeapCLRState`|사용자 지정 힙 덤프가 동적으로 할당 되지 않은 모든 런타임 상태 데이터를 수집 하도록 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 `ECustomDumpFlavor` 형식의 매개 변수는 [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) 메서드에 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ECustomDumpItemKind 열거형](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [ICLRErrorReportingManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
