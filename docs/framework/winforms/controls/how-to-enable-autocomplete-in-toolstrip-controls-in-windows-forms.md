---
title: '방법: ToolStrip 컨트롤에 자동 완성 기능 활성화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: db411023ad624e4c3d60b09bdbd588c85f8e22d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745511"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 컨트롤에 자동 완성 기능 활성화
다음 절차에서는 <xref:System.Windows.Forms.ToolStripLabel>를 삭제 하 여 최근에 방문한 웹 사이트와 같은 항목 목록을 표시할 수 있는 <xref:System.Windows.Forms.ToolStripComboBox>와 결합 합니다. 사용자가 목록에 있는 항목 중 하나의 첫 문자와 일치 하는 문자를 입력 하면 항목이 즉시 표시 됩니다.  
  
> [!NOTE]
> 자동 완성 기능은 <xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.TextBox>와 같은 일반적인 컨트롤에서 작동 하는 것과 동일한 방식으로 `ToolStrip` 컨트롤에서 작동 합니다.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>ToolStrip 컨트롤에서 자동 완성 기능을 사용 하도록 설정 하려면  
  
1. <xref:System.Windows.Forms.ToolStrip> 컨트롤을 만들고 여기에 항목을 추가 합니다.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. 레이블의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성을 설정 하 고 콤보 상자를 <xref:System.Windows.Forms.ToolStripItemOverflow.Never> 하 여 폼의 크기에 관계 없이 목록을 항상 사용할 수 있도록 합니다.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. <xref:System.Windows.Forms.ToolStripComboBox> 컨트롤의 Items 컬렉션에 단어를 추가 합니다.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. 콤보 상자의 <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> 속성을 <xref:System.Windows.Forms.AutoCompleteMode.Append>로 설정 합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. 콤보 상자의 <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> 속성을 <xref:System.Windows.Forms.AutoCompleteSource.ListItems>로 설정 합니다.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
