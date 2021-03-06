---
title: 4\.7의 F# 새로운 기능- F# 가이드
description: 4\.7에서 F# 사용할 수 있는 새 기능에 대 한 개요를 확인 하세요.
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644123"
---
# <a name="whats-new-in-f-47"></a>4\.7의 F# 새로운 기능

F#4.7는 언어에 대 한 F# 여러 가지 향상 된 기능을 추가 합니다.

## <a name="get-started"></a>시작

F#4.7는 모든 .NET Core 배포 및 Visual Studio 도구에서 사용할 수 있습니다. 를 [시작 F# ](../get-started/index.md) 하 여 자세히 알아보세요.

## <a name="language-version"></a>언어 버전

4\.7 F# 컴파일러는 프로젝트 파일의 속성을 통해 효과적인 언어 버전을 설정 하는 기능을 도입 합니다.

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

`4.6`, `4.7`, `latest`및 `preview`값으로 설정할 수 있습니다. 기본값은 `latest`입니다.

`preview`로 설정 하면 컴파일러는 컴파일러에서 구현 된 모든 F# 미리 보기 기능을 활성화 합니다.

## <a name="implicit-yields"></a>암시적 생성

더 이상 형식을 유추할 수 있는 배열, 목록, 시퀀스 또는 계산 식에 `yield` 키워드를 적용할 필요가 없습니다. 다음 예제에서는 두 식 모두 F# 4.7 이전의 각 항목에 대해 `yield` 문이 필요 합니다.

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [ 
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then 
            "Saturday"
            "Sunday"
    ] 
```

단일 `yield` 키워드를 도입 하는 경우 다른 모든 항목에도 `yield` 적용 되어 있어야 합니다.

시퀀스를 평면화 하는 것과 같은 작업을 수행 하는 `yield!` 사용 하는 식에 사용 하는 경우 암시적 생성은 활성화 되지 않습니다. 이러한 경우에는 현재 `yield`를 계속 사용 해야 합니다.

## <a name="wildcard-identifiers"></a>와일드 카드 식별자

클래스 F# 관련 코드에서 자체 식별자는 항상 멤버 선언에서 명시적 이어야 합니다. 그러나 자체 식별자가 사용 되지 않는 경우에는 일반적으로 이중 밑줄을 사용 하 여 이름이 지정 되지 않은 자체 식별자를 나타내는 것이 일반적입니다. 이제 단일 밑줄을 사용할 수 있습니다.

```fsharp
type C() =
    member _.M() = ()
```

이는 `for` 루프에도 적용 됩니다.

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>들여쓰기 relaxation

F# 4.7 이전에는 기본 생성자 및 정적 멤버 인수에 대 한 들여쓰기 요구 사항에 과도 한 들여쓰기가 필요 합니다. 이제 단일 들여쓰기 범위만 필요 합니다.

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
