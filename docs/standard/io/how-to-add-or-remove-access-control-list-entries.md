---
title: '방법: 액세스 제어 목록 항목 추가 또는 제거(.NET Framework에만 해당)'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
ms.openlocfilehash: 5f41c518b8732adff95593cab29d7085adcc9ab3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708130"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a>방법: 액세스 제어 목록 항목 추가 또는 제거(.NET Framework에만 해당)
파일 또는 디렉터리에서 ACL(액세스 제어 목록) 항목을 추가 또는 제거하려면, 파일 또는 디렉터리에서 <xref:System.Security.AccessControl.FileSecurity> 또는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져옵니다. 개체를 수정한 다음, 파일이나 디렉터리에 다시 적용합니다.  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a>파일에서 ACL 항목 추가 또는 제거  
  
1. <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> 메서드를 호출하여 파일의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.FileSecurity> 개체를 가져옵니다.  
  
2. 1단계에서 반환된 <xref:System.Security.AccessControl.FileSecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.  
  
3. 변경 내용을 적용하려면 <xref:System.Security.AccessControl.FileSecurity> 개체를 <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType> 메서드에 전달합니다.  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a>디렉터리에서 ACL 항목 추가 또는 제거  
  
1. <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> 메서드를 호출하여 디렉터리의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져옵니다.  
  
2. 1단계에서 반환된 <xref:System.Security.AccessControl.DirectorySecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.  
  
3. 변경 내용을 적용하려면 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType> 메서드에 전달합니다.  
  
## <a name="example"></a>예제  
 이 예제를 실행하려면 유효한 사용자 또는 그룹 계정을 사용해야 합니다. 예제에서는 <xref:System.IO.File> 개체를 사용합니다. <xref:System.IO.FileInfo>, <xref:System.IO.Directory> 및 <xref:System.IO.DirectoryInfo> 클래스에 동일한 프로시저를 사용합니다.

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
