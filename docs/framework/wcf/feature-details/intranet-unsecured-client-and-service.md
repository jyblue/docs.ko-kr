---
title: 보안이 설정되지 않은 인트라넷 클라이언트 및 서비스
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: 1ffd0421195b0339ad966b661c229e5a5ebb94ec
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212094"
---
# <a name="intranet-unsecured-client-and-service"></a>보안이 설정되지 않은 인트라넷 클라이언트 및 서비스
다음 그림은 WCF 응용 프로그램에 보안 개인 네트워크에 대 한 정보를 제공 하기 위해 개발 된 간단한 Windows Communication Foundation (WCF) 서비스를 보여 줍니다. 데이터가 중요 하지 않거나, 네트워크를 본질적으로 안전 하 게 보호 하거나, WCF 인프라 아래 계층에서 보안을 제공 하기 때문에 보안이 필요 하지 않습니다.  
  
 ![보안이 적용 되지 않은 인트라넷 클라이언트 및 서비스 시나리오](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|특징|설명|  
|--------------------|-----------------|  
|보안 모드|None|  
|Transport|TCP|  
|바인딩|<xref:System.ServiceModel.NetTcpBinding>|  
|상호 운용성|WCF만|  
|인증|None|  
|무결성|None|  
|기밀성|None|  
  
## <a name="service"></a>서비스  
 다음 코드와 구성은 독립적으로 실행되어야 합니다. 다음 작업 중 하나를 수행합니다.  
  
- 구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.  
  
- 제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.  
  
### <a name="code"></a>코드  
 다음 코드는 보안 없이 엔드포인트를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a>구성  
 다음 코드는 구성을 사용하여 동일한 엔드포인트를 설정합니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Client  
 다음 코드와 구성은 독립적으로 실행되어야 합니다. 다음 작업 중 하나를 수행합니다.  
  
- 이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.  
  
- 엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다. 대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다. 예를 들면 다음과 같습니다.:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>코드  
 다음 코드에서는 TCP 프로토콜을 사용 하 여 보안 되지 않은 끝점에 액세스 하는 기본 WCF 클라이언트를 보여 줍니다.  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a>구성  
 다음 구성 코드는 클라이언트에 적용됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.ServiceModel.NetTcpBinding>
- [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Windows Server Fabric 용 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
