---
title: ICorDebugModule2::ApplyChanges 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
ms.openlocfilehash: c324019e1e62701f4f2aaba1c00948b292ba6847
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127905"
---
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges 메서드
메타 데이터의 변경 내용과 MSIL (Microsoft 중간 언어) 코드의 변경 내용을 실행 중인 프로세스에 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cbMetadata`  
 진행 델타 메타 데이터의 크기 (바이트)입니다.  
  
 `pbMetadata`  
 진행 델타 메타 데이터를 포함 하는 버퍼입니다. 버퍼의 주소는 [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) 메서드에서 반환 됩니다.  
  
 메타 데이터의 Rva (상대 가상 주소)는 MSIL 코드의 시작 부분을 기준으로 해야 합니다.  
  
 `cbIL`  
 진행 델타 MSIL 코드의 크기 (바이트)입니다.  
  
 `pbIL`  
 진행 업데이트 된 MSIL 코드를 포함 하는 버퍼입니다.  
  
## <a name="remarks"></a>주의  
 `pbMetadata` 매개 변수는 특수 한 델타 메타 데이터 형식으로 되어 있습니다 ( [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)에서 출력). `pbMetadata`는 이전 메타 데이터를 기본으로 사용 하 고 해당 기준에 적용할 개별 변경 내용을 설명 합니다.  
  
 이와 대조적으로, `pbIL[`] 매개 변수는 업데이트 된 메서드에 대 한 새 MSIL을 포함 하 고 해당 메서드에 대 한 이전 MSIL을 완전히 대체 하기 위한 것입니다.  
  
 델타 MSIL 및 메타 데이터를 디버거의 메모리에 만든 경우 디버거는 `ApplyChanges`를 호출 하 여 변경 내용을 CLR (공용 언어 런타임)로 보냅니다. 런타임에서는 메타 데이터 테이블을 업데이트 하 고, 새 MSIL을 프로세스에 배치 하 고, 새 MSIL의 JIT (just-in-time) 컴파일을 설정 합니다. 변경 내용이 적용 되 면 디버거는 [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) 를 호출 하 여 다음 편집 세션을 준비 해야 합니다. 그러면 디버거가 프로세스를 계속할 수 있습니다.  
  
 디버거가 델타 메타 데이터를 포함 하는 모듈에 대해 `ApplyChanges`를 호출할 때마다 변경 내용을 내보내는 데 사용 되는 복사를 제외 하 고 해당 모듈의 메타 데이터 복사본 모두에 대해 동일한 델타 메타 데이터를 사용 하 여 [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) 를 호출 해야 합니다. 메타 데이터의 복사본이 실제 메타 데이터와 동기화 되지 않을 경우 디버거는 항상 새 복사본을 복사 하 고 가져오는 것을 항상 throw 할 수 있습니다.  
  
 `ApplyChanges` 메서드가 실패 하면 디버그 세션의 상태가 잘못 되어 다시 시작 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
