---
title: 비관리형 형식 - C# 참조
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 042cf382879cc4010a388fb75f41099b4342c9d9
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626947"
---
# <a name="unmanaged-types-c-reference"></a>비관리형 형식(C# 참조)

형식이 다음 형식 중 하나인 경우에는 **관리되지 않는 형식**입니다.

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` 또는 `bool`
- 임의의 [열거형](enum.md) 형식
- 임의의 [포인터](../../programming-guide/unsafe-code-pointers/pointer-types.md) 형식
- 관리되지 않는 형식의 필드만 포함하고 C# 7.3 및 이전 버전에서 사용자 정의된 [구조체](struct.md) 형식은 생성 형식(하나 이상의 형식 인수를 포함하는 형식)이 아닙니다.

C# 7.3부터 [`unmanaged` 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)을 사용하여 형식 매개 변수가 nullable이 아니며 비포인터 및 비관리형 형식임을 지정할 수 있습니다.

C# 8.0부터는 다음 예와 같이 관리되지 않는 형식의 필드만 포함하는 *생성된* 구조체 형식도 관리되지 않습니다.

[!code-csharp[unmanaged constructed types](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#ProgramExample)]

제네릭 구조체는 관리되는 구조체 및 관리되지 않는 구조체 형식 모두의 원본일 수 있습니다. 위의 예에서는 제네릭 구조체 `Coords<T>`를 정의하고 관리되지 않는 생성 형식의 예를 보여 줍니다. 관리되지 않는 형식이 아닌 예는 `Coords<object>`입니다. 관리되지 않는 `object` 형식의 필드가 있기 때문에 관리되지 않습니다. *모든* 생성 형식을 관리되지 않는 형식으로 하려면 제네릭 구조체의 정의에서 `unmanaged` 제약 조건을 사용합니다.

[!code-csharp[unmanaged constraint in type definition](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [포인터 형식](~/_csharplang/spec/unsafe-code.md#pointer-types) 섹션을 참조하세요.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [메모리 및 범위 관련 형식](../../../standard/memory-and-spans/index.md)
- [sizeof 연산자](../operators/sizeof.md)
- [stackalloc 연산자](../operators/stackalloc.md)
