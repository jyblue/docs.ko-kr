---
title: '방법: 읽기 전용 텍스트 상자 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 17ae9524009c687cd62fb315f842e188e120ac68
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731276"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>방법: 읽기 전용 텍스트 상자 만들기(Windows Forms)

편집 가능한 Windows Forms 텍스트 상자를 읽기 전용 컨트롤로 변환할 수 있습니다. 예를 들어 텍스트 상자에는 일반적으로 편집 되지만 응용 프로그램의 상태로 인해 현재는 표시 되지 않는 값이 표시 될 수 있습니다.

## <a name="to-create-a-read-only-text-box"></a>읽기 전용 텍스트 상자를 만들려면

1. <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성을 `true`로 설정 합니다. 속성이 `true`로 설정 된 상태에서 사용자는 변경 내용을 허용 하지 않고 텍스트 상자의 텍스트를 스크롤하고 강조 표시할 수 있습니다. 텍스트 상자에서 **복사** 명령이 작동 하지만 **잘라내기** 및 **붙여넣기** 명령은 사용할 수 없습니다.

    > [!NOTE]
    > <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성은 런타임에 사용자 상호 작용에만 영향을 줍니다. 텍스트 상자의 <xref:System.Windows.Forms.TextBox.Text%2A> 속성을 변경 하 여 런타임에 텍스트 상자 콘텐츠를 프로그래밍 방식으로 변경할 수 있습니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.TextBox>
- [TextBox 컨트롤 개요](textbox-control-overview-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [방법: 문자열에 인용 부호 넣기](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox 컨트롤](textbox-control-windows-forms.md)
