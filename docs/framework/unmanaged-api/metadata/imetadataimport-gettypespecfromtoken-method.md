---
title: IMetaDataImport::GetTypeSpecFromToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
ms.openlocfilehash: 3ab24ab869e1f2cff9beafe50e6982ba2e7cf0aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436699"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a>IMetaDataImport::GetTypeSpecFromToken 메서드
지정한 토큰이 나타내는 형식 사양의 이진 메타데이터 서명을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `typespec`  
 진행 요청 된 메타 데이터 시그니처와 연결 된 TypeSpec 토큰입니다.  
  
 `ppvSig`  
 제한이 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `pcbSig`  
 제한이 메타 데이터 시그니처의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 또는 실패를 나타내는 HRESULT입니다. 실패 한 매크로를 사용 하 여 오류를 테스트할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
