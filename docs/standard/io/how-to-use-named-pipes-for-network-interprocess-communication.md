---
title: '방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communication [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
ms.openlocfilehash: 71f3a8d38b46993762b2673ea5fe735d8d54d351
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706636"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용
명명된 파이프는 파이프 서버와 하나 이상의 파이프 클라이언트 간의 프로세스 간 통신을 제공합니다. 로컬 컴퓨터에서 프로세스 간 통신을 제공하는 익명 파이프보다 많은 기능을 제공합니다. 명명된 파이프는 네트워크 및 다중 서버 인스턴스를 통한 양방향 통신, 메시지 기반 통신 및 연결 프로세스가 원격 서버에서 고유한 권한 집합을 사용할 수 있는 클라이언트 가장을 지원합니다.  
  
 명명된 파이프를 구현하려면, <xref:System.IO.Pipes.NamedPipeServerStream> 및 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 <xref:System.IO.Pipes.NamedPipeServerStream> 클래스를 사용하여 명명된 파이프를 생성하는 방법을 보여줍니다. 이 예제에서 서버 프로세스는 네 개의 스레드를 생성합니다. 각 스레드는 클라이언트 연결을 허용할 수 있습니다. 연결된 클라이언트 프로세스는 서버에 파일 이름을 제공합니다. 클라이언트에 충분한 권한이 있는 경우 서버 프로세스는 파일을 열고 콘텐츠를 클라이언트에 다시 보냅니다.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>예제  
 다음 예제는 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용하는 클라이언트 프로세스를 보여줍니다. 클라이언트는 서버 프로세스에 연결하여 서버에 파일 이름을 보냅니다. 이 예제에서는 가장을 사용하므로 클라이언트 애플리케이션을 실행하는 ID에는 파일에 액세스할 수 있는 권한이 있어야 합니다. 그런 다음, 서버는 파일의 내용을 클라이언트로 다시 보냅니다. 그러면 파일의 내용이 콘솔에 표시됩니다.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 예제의 클라이언트 및 서버 프로세스는 동일한 컴퓨터에서 실행되므로 <xref:System.IO.Pipes.NamedPipeClientStream> 개체에 제공된 서버 이름은 `"."`입니다. 클라이언트 및 서버 프로세스가 별도의 컴퓨터에 있는 경우 `"."`는 서버 프로세스를 실행하는 컴퓨터의 네트워크 이름으로 대체됩니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [파이프](../../../docs/standard/io/pipe-operations.md)
- [방법: 로컬 프로세스 간 통신에 익명 파이프 사용](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
