---
title: Windows 应用商店应用的网络隔离
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 34b8865781079f45a68d3dd1aab7fbd66c703d50
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447418"
---
# <a name="network-isolation-for-windows-store-apps"></a>Windows 应用商店应用的网络隔离
<xref:System.Net>、<xref:System.Net.Http> 和 <xref:System.Net.Http.Headers> 命名空间中的类可用于开发 Windows 应用商店应用或桌面应用。 在 Windows 应用商店应用中使用时，这些命名空间中的类会受到网络隔离（[!INCLUDE[win8](../../../includes/win8-md.md)] 使用的应用程序安全模型的一部分）的影响。 必须在应用清单中为 Windows 应用商店应用启用适当的网络功能，以便系统允许网络访问。  
  
## <a name="checklist-for-network-isolation"></a>网络隔离的核对清单  
 使用此清单以确保为 Windows 应用商店应用配置了网络隔离。  
  
1. 确定应用所需网络访问请求的方向。 这可以是出站客户端发起的请求或入站主动提供的请求，也可以是这两种网络请求类型的组合。  
  
2. 确定该应用将与之通信的网络资源类型。 应用可能需要与家庭或工作网络上受信任的资源进行通信。 应用可能需要与 Internet 上的资源进行通信。 应用可能需要访问两种类型的网络资源。  
  
3. 在应用程序清单中配置最低要求的网络隔离功能。  
  
4. 部署并运行应用，使用为故障排除提供的网络隔离工具进行测试。  
  
 有关如何配置用于网络隔离故障排除的网络功能和隔离工具的详细信息，请参阅 Windows 8.x 应用商店开发人员文档中的[如何配置网络隔离功能](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))。
  
## <a name="see-also"></a>请参阅

- [连接到 Web 服务](https://docs.microsoft.com/previous-versions/windows/apps/hh761504(v=win.10))
- [网络隔离指南和核对清单](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))
- [快速入门：使用 HttpClient 进行连接](https://docs.microsoft.com/previous-versions/windows/apps/hh781239(v=win.10))
- [如何使用 HttpClient 处理程序](https://docs.microsoft.com/previous-versions/windows/apps/hh781241(v=win.10))
- [如何确保 HttpClient 连接安全](https://docs.microsoft.com/previous-versions/windows/apps/hh781240(v=win.10))
- [HttpClient 示例](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
