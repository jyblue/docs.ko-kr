---
title: ICLRSyncManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
ms.openlocfilehash: 3593e4d68058a1820f575c92ff9571d43560316a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133927"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager 인터페이스
호스트에서 요청 된 작업에 대 한 정보를 가져오고 해당 동기화 구현에서 교착 상태를 검색할 수 있도록 하는 메서드를 정의 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator 메서드](iclrsyncmanager-createrwlockowneriterator-method.md)|CLR (공용 언어 런타임)이 판독기-작성기 잠금을 기다리는 작업 집합을 결정 하는 데 사용할 반복기를 호스트에 만들도록 요청 합니다.|  
|[DeleteRWLockOwnerIterator 메서드](iclrsyncmanager-deleterwlockowneriterator-method.md)|`CreateRWLockOwnerIterator`에 대 한 호출로 생성 된 반복기를 CLR에서 삭제 하도록 요청 합니다.|  
|[GetMonitorOwner 메서드](iclrsyncmanager-getmonitorowner-method.md)|지정 된 모니터를 소유 하는 작업을 가져옵니다.|  
|[GetRWLockOwnerNext 메서드](iclrsyncmanager-getrwlockownernext-method.md)|현재 판독기-작성기 잠금을 기다리는 다음 작업을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- <xref:System.Threading.Thread>
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
- [관리 되는 스레딩 및 관리 되지 않는 스레딩](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [호스팅 인터페이스](hosting-interfaces.md)
