---
title: 추가 도구
description: .NET Core 기능을 지원하고 확장하는, 설치 가능한 추가 도구에 대한 개요입니다.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: c0224a1cc6cbb9ae6fa88e5f869c47a1e84289e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451527"
---
# <a name="net-core-additional-tools-overview"></a>.NET Core 추가 도구 개요

이 섹션에서는 .NET Core CLI 외에 .NET Core 기능을 지원하고 확장하는 도구 목록을 소개합니다.

## <a name="net-core-uninstall-tool"></a>.NET Core 제거 도구

[.NET Core 제거 도구](https://github.com/dotnet/cli-lab/releases)(`dotnet-core-uninstall`)를 사용하면 지정한 버전만 유지되도록 시스템에서 .NET Core SDK 및 런타임을 정리할 수 있습니다. 제거되는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.

## <a name="net-core-diagnostic-tools"></a>.NET Core 진단 도구

[dotnet-counters](../diagnostics/dotnet-counters.md)는 1단계 상태 모니터링 및 성능 조사를 위한 성능 모니터링 도구입니다.

[dotnet-dump](../diagnostics/dotnet-dump.md)는 네이티브 디버거 없이 Windows 및 Linux 코어 덤프를 수집하고 분석하는 방법을 제공합니다.

[dotnet-trace](../diagnostics/dotnet-trace.md)는 앱이 느리게 실행되는 이유를 확인해야 하는 시나리오에서 도움이 될 수 있는 프로파일링 데이터를 앱에서 수집합니다.

## <a name="wcf-web-service-reference-tool"></a>WCF Web Service Reference 도구

WCF(Windows Communication Foundation) [Web Service Reference 도구](wcf-web-service-reference-guide.md)는 [Visual Studio 2017 버전 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools)에서 처음 공개된 Visual Studio 연결된 서비스 공급자입니다. 이 도구는 WSDL 파일, 네트워크 위치 또는 현재 솔루션의 웹 서비스에서 메타데이터를 검색합니다. 웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET Core와 호환되는 소스 파일을 생성합니다.

## <a name="wcf-dotnet-svcutil-tool"></a>WCF dotnet-svcutil 도구

WCF [dotnet-svcutil 도구](dotnet-svcutil-guide.md)는 WSDL 파일 또는 네트워크 위치의 웹 서비스에서 메타데이터를 검색하는 .NET 도구입니다. 웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET Core와 호환되는 소스 파일을 생성합니다.

**dotnet-svcutil** 도구는 Visual Studio 2017 버전 15.5와 함께 처음 제공된 [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio 연결 서비스 공급자를 대체하는 옵션입니다. .NET 도구인 **dotnet-svcutil** 도구는 Linux, macOS 및 Windows에서 사용할 수 있습니다.

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a>WCF dotnet-svcutil.xmlserializer 도구

.NET Framework에서 svcutil 도구를 사용하여 serialization 어셈블리를 미리 생성할 수 있습니다. WCF [dotnet-svcutil.xmlserializer 도구](dotnet-svcutil.xmlserializer-guide.md)는 .NET Core에서 유사한 기능을 제공합니다. WCF 서비스 계약에서 사용되고 <xref:System.Xml.Serialization.XmlSerializer>를 통해 직렬화할 수 있는 클라이언트 애플리케이션의 형식에 대해 C# serialization 코드를 미리 생성합니다. 이렇게 하면 해당 형식의 개체를 직렬화 또는 역직렬화할 때 XML serialization의 시작 성능이 향상됩니다.

## <a name="xml-serializer-generator"></a>XML Serializer Generator

.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET Core 및 .NET Standard 라이브러리용 솔루션입니다. <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.
