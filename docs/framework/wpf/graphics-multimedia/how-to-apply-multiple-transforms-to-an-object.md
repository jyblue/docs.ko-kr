---
title: '방법: 개체에 다중 변환 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 544d0a26f24e5ad4ed7e2e3cfa25f8e15d1be446
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452833"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>방법: 개체에 다중 변환 적용
이 예제에서는 <xref:System.Windows.Media.TransformGroup>를 사용 하 여 둘 이상의 <xref:System.Windows.Media.Transform> 개체를 단일 복합 <xref:System.Windows.Media.Transform>그룹화 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Media.TransformGroup>를 사용 하 여 <xref:System.Windows.Media.ScaleTransform> 및 <xref:System.Windows.Media.RotateTransform>를 <xref:System.Windows.Controls.Button>에 적용 합니다.  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [Transform 개요](transforms-overview.md)
- [2차원 변환 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
