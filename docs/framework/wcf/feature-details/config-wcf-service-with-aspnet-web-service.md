---
title: 如何：配置 WCF 服务以便与 ASP.NET Web 服务客户端进行互操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 6a06e1983a54581cfb89f008e9f063a671e992c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185352"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>如何：配置 WCF 服务以便与 ASP.NET Web 服务客户端进行互操作
要将 Windows 通信基础 （WCF） 服务终结点配置为与 ASP.NET Web 服务客户端<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>进行互操作，请使用 该类型作为服务终结点的绑定类型。  
  
 你可以根据需要在该绑定上启用对 HTTPS 和传输级客户端身份验证的支持。 ASP.NET Web 服务客户端不支持 MTOM 消息编码，<xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>因此该属性应保留为其默认值，即<xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>。 ASP.Net Web 服务客户端不支持 WS-Security，所以应将 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 设置为 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>。  
  
 要使 WCF 服务的元数据可用于 ASP.NET Web 服务代理生成工具（即[Web 服务描述语言工具 （Wsdl.exe）、Web](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100))[服务发现工具 （Disco.exe）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))和 Visual Studio 中的添加 Web 引用功能），应公开 HTTP/GET 元数据终结点。  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>在代码中添加与 ASP.NET Web 服务客户端兼容的 WCF 终结点  
  
1. 创建一个新的 <xref:System.ServiceModel.BasicHttpBinding> 实例。  
  
2. （可选）将此服务终结点绑定的安全模式设置为 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>，从而为此绑定启用传输安全。 有关详细信息，请参阅[运输安全](../../../../docs/framework/wcf/feature-details/transport-security.md)。  
  
3. 使用刚创建的绑定实例，向服务主机添加一个新的应用程序终结点。 有关如何在代码中添加服务终结点的详细信息，请参阅[如何：在代码中创建服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)。  
  
4. 为服务启用一个 HTTP/GET 元数据终结点。 有关详细信息，请参阅[：使用代码发布服务的元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)。  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>在配置文件中添加与 ASP.NET Web 服务客户端兼容的 WCF 终结点  
  
1. 创建一个新的 <xref:System.ServiceModel.BasicHttpBinding> 绑定配置。 有关详细信息，请参阅[如何：在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。  
  
2. （可选）将此服务终结点绑定的安全模式设置为 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>，从而为此绑定配置启用传输安全。 有关详细信息，请参阅[运输安全](../../../../docs/framework/wcf/feature-details/transport-security.md)。  
  
3. 使用刚创建的绑定配置，为服务配置一个新的应用程序终结点。 有关如何在配置文件中添加服务终结点的详细信息，请参阅[如何：在配置 中创建服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)。  
  
4. 为服务启用一个 HTTP/GET 元数据终结点。 有关详细信息，请参阅[如何：使用配置文件发布服务的元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。  
  
## <a name="example"></a>示例  
 下面的示例代码演示如何在代码和配置文件中添加与ASP.NET Web 服务客户端兼容的 WCF 终结点。  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>另请参阅

- [如何：在代码中创建服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [如何：使用代码发布服务的元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [如何：在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [如何：在配置中创建服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [如何：使用配置文件发布服务的元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [运输安全](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [使用元数据](../../../../docs/framework/wcf/feature-details/using-metadata.md)
