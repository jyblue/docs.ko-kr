---
title: ASSEMBLYMETADATA 구조체
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444261"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA 구조체
참조 된 어셈블리에 대 한 버전 및 로캘, 프로세서 및 운영 체제에 대 한 지원 수준을 포함 하 여 참조 되는 어셈블리에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`usMajorVersion`|참조 된 어셈블리의 주 버전 번호입니다. 이 값은 0 일 수 없습니다. `usMajorVersion`의 모든 비트가 설정 되어 있으면 주 버전이 지정 되지 않습니다.|  
|`usMinorVersion`|참조 된 어셈블리의 부 버전 번호입니다. 이 값은 0 일 수 없습니다. `usMinorVersion`의 모든 비트가 설정 된 경우 부 버전은 지정 되지 않습니다.|  
|`usBuildNumber`|참조 된 어셈블리의 빌드 번호입니다. 이 값은 0 일 수 없습니다. `usBuildNumber`의 모든 비트가 설정 되어 있으면 빌드 번호가 지정 되지 않습니다.|  
|`usRevisionNumber`|참조 된 어셈블리의 수정 번호입니다. 이 값은 0 일 수 없습니다. `usRevisionNumber`의 모든 비트가 설정 된 경우 수정 번호는 지정 되지 않습니다.|  
|`szLocale`|RFC1766 사양을 준수 하 고 세미콜론으로 구분 된 로캘 이름 목록으로, 참조 된 어셈블리에서 지원 되는 로캘을 지정 합니다. Null 값은 로캘과 관련이 없음을 나타냅니다. **참고:**  .NET Framework 버전 1.0에서는 둘 이상의 로캘을 지정할 수 없습니다.|  
|`cbLocale`|`szLocale`의 와이드 문자 크기입니다.|  
|`rdwProcessor`|참조 된 어셈블리에서 지원 되는 프로세서 형식에 대해 Winnt.exe에 정의 된 식별자의 배열입니다. NULL 값은 프로세서 독립성을 나타냅니다.|  
|`ulProcessor`|`rdwProcessor` 배열의 길이입니다.|  
|`rOS`|참조 된 어셈블리에서 지 원하는 운영 체제를 지정 하는 [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) 인스턴스의 배열입니다. NULL 값은 운영 체제 독립성을 나타냅니다.|  
|`ulOS`|`rOS` 배열의 길이입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 구조체](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [OSINFO 구조체](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
