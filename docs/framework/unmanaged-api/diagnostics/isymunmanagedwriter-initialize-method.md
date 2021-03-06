---
title: ISymUnmanagedWriter::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 6e9ab623d5fe9fcfda2305df078e988a561afdc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427968"
---
# <a name="isymunmanagedwriterinitialize-method"></a>ISymUnmanagedWriter::Initialize 메서드
이 작성기를 연결할 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 쓸 출력 파일 이름을 설정 합니다.  
  
 이 메서드는 한 번만 호출할 수 있으며 다른 작성기 메서드 보다 먼저 호출 해야 합니다. 일부 작성기에는 파일 이름이 필요할 수 있습니다. 그러나 파일 이름을 사용 하지 않는 작성기에는 부정적인 영향을 주지 않으면 서 항상이 메서드에 파일 이름을 전달할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a>매개 변수  
 `emitter`  
 진행 메타 데이터 내보내기 인터페이스에 대 한 포인터입니다.  
  
 `filename`  
 진행 디버깅 기호를 쓸 파일 이름입니다. 파일 이름을 사용하지 않는 작성기에 대해 파일 이름이 지정되면 이 매개 변수는 무시됩니다.  
  
 `pIStream`  
 진행 지정 된 경우 기호 작성기는 `filename` 매개 변수에 지정 된 파일이 아닌 지정 된 <xref:System.Runtime.InteropServices.ComTypes.IStream>에 기호를 내보냅니다. `pIStream` 매개 변수는 선택적 요소입니다.  
  
 `fFullBuild`  
 [in] 전체 다시 작성 인 경우 `true` 합니다. 증분 컴파일 인 경우 `false` 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize2 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
