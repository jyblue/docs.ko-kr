---
title: ICLRTaskManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092196"
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager 인터페이스
호스트에서 CLR (공용 언어 런타임)이 새 작업을 만들고, 현재 실행 중인 작업을 가져오고, 작업의 지리적 언어와 문화권을 설정할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateTask 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|CLR이 새 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 만들도록 명시적으로 요청 합니다.|  
|[GetCurrentTask 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|현재 실행 중인 작업을 나타내는 `ICLRTask` 인스턴스를 가져옵니다.|  
|[GetCurrentTaskType 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|현재 실행 중인 작업의 형식을 가져옵니다.|  
|[SetLocale 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|호스트에서 현재 실행 중인 작업의 로캘 식별자를 수정 했음을 CLR에 알립니다.|  
|[SetUILocale 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|호스트에서 현재 실행 중인 작업의 사용자 인터페이스 로캘 식별자를 수정 했음을 공용 언어 런타임에 알립니다.|  
  
## <a name="remarks"></a>주의  
 호스팅된 환경에서 실행 되는 각 작업에는 호스트 측 ( [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)의 인스턴스) 및 CLR 쪽 ( [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)의 인스턴스) 모두에 대 한 표현이 있습니다. 호스트 또는 CLR에서 작업 만들기를 시작할 수 있지만 호스트와 작업에 대 한 CLR 간의 성공적인 통신을 보장 하기 위해 호스트 쪽 표현이 해당 CLR 쪽 표현과 연결 되어야 합니다. 운영 체제 스레드에서 관리 코드를 실행 하려면 먼저 두 개체를 만들고 인스턴스화해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
