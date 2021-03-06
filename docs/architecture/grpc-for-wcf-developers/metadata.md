---
title: WCF 개발자를 위한 메타 데이터 gRPC
description: GRPC에서 메타 데이터를 사용 하 여 클라이언트와 서버 간에 추가 컨텍스트를 전달 하는 방법입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 64fa94d1e63af480cbc7363631de161c5b8b8fb8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628581"
---
# <a name="metadata"></a>메타데이터

*메타 데이터* 는 요청 및 응답을 처리 하는 동안 유용할 수 있지만 실제 응용 프로그램 데이터에 포함 되지 않는 추가 데이터를 나타냅니다. 메타 데이터에는 모니터링 목적으로 사용할 수 있는 인증 토큰, 요청 식별자 및 태그, 데이터 집합의 레코드 수와 같은 데이터에 대 한 정보가 포함 될 수 있습니다.

<xref:System.ServiceModel.OperationContextScope> 및 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> 속성을 사용 하 여 Windows Communication Foundation (WCF) 메시지에 제네릭 키/값 헤더를 추가 하 고 <xref:System.ServiceModel.Channels.MessageProperties>를 사용 하 여 처리할 수 있습니다.

gRPC 호출 및 응답에는 HTTP 헤더와 유사한 메타 데이터가 포함 될 수도 있습니다. 이 메타 데이터는 대부분 gRPC 자체에 표시 되지 않으며 응용 프로그램 코드 또는 미들웨어에서 처리 하기 위해 전달 됩니다. 메타 데이터는 키/값 쌍으로 표현 됩니다. 여기서 키는 문자열이 고 값은 문자열 또는 이진 데이터입니다. `.proto` 파일에서 메타 데이터를 지정할 필요가 없습니다.

메타 데이터는 [Grpc](https://www.nuget.org/packages/Grpc.Core.Api/) 의 `Metadata` 클래스인 NuGet 패키지에서 처리 됩니다. 이 클래스는 컬렉션 이니셜라이저 구문과 함께 사용할 수 있습니다.

이 예제에서는 C# 클라이언트에서 호출에 메타 데이터를 추가 하는 방법을 보여 줍니다.

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

gRPC 서비스는 `ServerCallContext` 인수의 `RequestHeaders` 속성에서 메타 데이터에 액세스할 수 있습니다.

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

서비스는 `ServerCallContext`의 `ResponseTrailers` 속성을 사용 하 여 클라이언트에 메타 데이터를 보낼 수 있습니다.

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
>[이전](rpc-types.md)
>[다음](error-handling.md)
