---
title: SqlStreamChars.Length 속성 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ac6e6af9c9411ebc25039e0992133fae2b35ee23
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221183"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="a8753-102">SqlStreamChars.Length 속성</span><span class="sxs-lookup"><span data-stu-id="a8753-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="a8753-103">파생된 클래스에서 재정의 되 면 현재 스트림의 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="a8753-104">이 속성을 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="a8753-105">SQL Server에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="a8753-106">다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8753-107">구문</span><span class="sxs-lookup"><span data-stu-id="a8753-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="a8753-108">속성 값</span><span class="sxs-lookup"><span data-stu-id="a8753-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="a8753-109">스트림의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8753-110">설명</span><span class="sxs-lookup"><span data-stu-id="a8753-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a8753-111">`SqlStreamChars.Length` 속성은 전용 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a8753-112">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8753-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8753-113">Requirements</span></span>

<span data-ttu-id="a8753-114">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="a8753-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="a8753-115">**어셈블리:** System.Data (System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="a8753-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="a8753-116">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8753-116">**.NET Framework versions:** Available since 2.0.</span></span>