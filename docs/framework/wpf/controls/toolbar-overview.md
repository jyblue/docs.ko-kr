---
title: ToolBar 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 460d4420d5faf849a8d05a94e0170aea384f69b4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452697"
---
# <a name="toolbar-overview"></a>ToolBar 개요
<xref:System.Windows.Controls.ToolBar> 컨트롤은 일반적으로 해당 함수와 관련 된 명령 또는 컨트롤 그룹의 컨테이너입니다. 일반적으로 <xref:System.Windows.Controls.ToolBar>는 명령을 호출 하는 단추를 포함 합니다.  

<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>ToolBar 컨트롤  
 <xref:System.Windows.Controls.ToolBar> 컨트롤은 단추나 다른 컨트롤의 막대와 비슷한 배열에서 단일 행 또는 열로 이름을 가져옵니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 컨트롤은 크기 제한 <xref:System.Windows.Controls.ToolBar> 내에 자연스럽 게 맞지 않는 모든 항목을 특수 오버플로 영역에 배치 하는 오버플로 메커니즘을 제공 합니다. 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 컨트롤은 일반적으로 특정 레이아웃 동작을 제공 하는 관련 <xref:System.Windows.Controls.ToolBarTray> 컨트롤과 함께 사용 되며 사용자가 시작 하는 크기 조정 및 도구 모음의 정렬을 지원 합니다.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>ToolBarTray에서 ToolBar 위치 지정  
 <xref:System.Windows.Controls.ToolBar.Band%2A> 및 <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 속성을 사용 하 여 <xref:System.Windows.Controls.ToolBar>를 <xref:System.Windows.Controls.ToolBarTray>에 배치 합니다. <xref:System.Windows.Controls.ToolBar.Band%2A> <xref:System.Windows.Controls.ToolBar> 부모 <xref:System.Windows.Controls.ToolBarTray>내에 배치 되는 위치를 나타냅니다. <xref:System.Windows.Controls.ToolBar.BandIndex%2A>는 <xref:System.Windows.Controls.ToolBar> 밴드 내에서 배치 되는 순서를 나타냅니다. 다음 예제에서는 배치에이 속성을 사용 방법 <xref:System.Windows.Controls.ToolBar> 내부의 컨트롤을 <xref:System.Windows.Controls.ToolBarTray>입니다.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>오버플로 항목이 있는 ToolBar  
 도구 모음 크기에 맞출 수 있는 것 보다 많은 항목이 <xref:System.Windows.Controls.ToolBar> 컨트롤에 포함 되는 경우가 많습니다. 이 경우 <xref:System.Windows.Controls.ToolBar>는 오버플로 단추를 표시 합니다. 오버플로 항목을 보기 위해 사용자는 오버플로 단추를 클릭 하면 항목이 <xref:System.Windows.Controls.ToolBar>아래의 팝업 창에 표시 됩니다. 다음 그림은 오버플로 항목이 있는 <xref:System.Windows.Controls.ToolBar>를 보여 줍니다.  
  
 ![오버플로 항목이 있는 도구 모음을 보여 주는 스크린샷](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> 연결 된 속성을 <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>또는 <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>설정 하 여 도구 모음의 항목이 오버플로 패널에 배치 되는 경우를 지정할 수 있습니다. 다음 예제에서는 도구 모음에 있는 마지막 네 개의 단추가 오버플로 패널에 항상 표시되도록 지정합니다.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> <xref:System.Windows.Controls.Primitives.ToolBarPanel> 및 <xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>를 사용 합니다.  <xref:System.Windows.Controls.Primitives.ToolBarPanel> 도구 모음에 있는 항목의 레이아웃을 담당 합니다.  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>는 <xref:System.Windows.Controls.ToolBar>에 맞지 않는 항목의 레이아웃을 담당 합니다. <xref:System.Windows.Controls.ToolBar>에 대 한 <xref:System.Windows.Controls.ControlTemplate> 예제는를 참조 하세요.  
  
 [ToolBar 스타일 및 템플릿](toolbar-styles-and-templates.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [ToolBar 컨트롤의 스타일 지정](how-to-style-controls-on-a-toolbar.md)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)(WPF 컨트롤 갤러리 샘플)
