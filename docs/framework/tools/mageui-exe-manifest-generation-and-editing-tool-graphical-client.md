---
title: MageUI.exe（图形化客户端中的清单生成和编辑工具）
ms.date: 03/30/2017
helpviewer_keywords:
- Manifest Generation and Editing tool
- MageUI.exe
ms.assetid: f9e130a6-8117-49c4-839c-c988f641dc14
ms.openlocfilehash: 99f522181232d16b9913ba3c55f34274b75d8966
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449411"
---
# <a name="mageuiexe-manifest-generation-and-editing-tool-graphical-client"></a>MageUI.exe（图形化客户端中的清单生成和编辑工具）

除了使用基于 Windows 的用户界面 (UI) 之外，MageUI.exe 与命令行工具 Mage.exe 支持的功能完全相同。 使用此工具，你可以对部署清单和应用程序清单执行创建、编辑和签名操作。 用 MageUI.exe 创建的新清单以 [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] 为目标。 早期版本的 MageUI.exe 应用于以 .NET Framework 的早期版本为目标。 在清单中添加或删除程序集时或重新对现有清单签名时，MageUI.exe 不会将清单更新为以 [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] 为目标。 有关详细信息，请参阅 [Mage.exe（清单生成和编辑工具）](mage-exe-manifest-generation-and-editing-tool.md)。

 此工具会自动随 Visual Studio 一起安装。 若要运行此工具，请使用 Visual Studio 开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。 有关详细信息，请参阅[命令提示](developer-command-prompt-for-vs.md)。

 Mage.exe 和 MageUI.exe 的两个版本作为组件包含在 Visual Studio 中。 若要查看版本信息，请运行 MageUI.exe，选择 **“帮助”** 并选择 **“关于”** 。 本文档描述 Mage.exe 和 MageUI.exe 的 4.0.x.x 版本。

> [!NOTE]
> 使用 MageUI.exe 保存已用证书签名的应用程序清单时，MageUI.exe 不支持 [compatibleFrameworks](/visualstudio/deployment/compatibleframeworks-element-clickonce-deployment) 元素。 这种情况下必须使用 [Mage.exe](mage-exe-manifest-generation-and-editing-tool.md)。  
  
## <a name="uielement-list"></a>UIElement 列表  
 下表列出了可用的菜单项和工具栏项。  
  
|命令|菜单|快捷键|说明|  
|-------------|----------|--------------|-----------------|  
|**应用程序清单**|**文件，新建**||创建新的应用程序清单。|  
|**部署清单**|**文件，新建**||创建新的部署清单。|  
|**打开**|**文件**|Ctrl+O|打开现有的部署清单、应用程序清单或信任许可证以进行编辑。|  
|**关闭**|**文件**|Ctrl+F4|关闭打开的文件。<br /><br /> 如果在关闭文件之前修改文件，则 MageUI.exe 将提示你使用公钥、密钥对或存储的证书对文件重新进行签名。|  
|**保存**|**文件**|Ctrl+S|将当前具有用户输入焦点的文档保存到磁盘。|  
|**另存为**|**文件**||将文件保存到磁盘，使你能够提供新的文件名和/或位置。|  
|**全部保存**|**文件**||保存对 MageUI.exe 中当前打开的全部文件所做的更改。|  
|**首选项**|**文件**||打开“首选项”  对话框。 有关详细信息，请参阅下一节。|  
|<bpt id="p1">**</bpt>Exit<ept id="p1">**</ept>|**文件**|Alt + F4|退出 MageUI.exe。|  
|**剪切**|**编辑**|Ctrl+X|从应用程序中移除当前选定的文本，然后将其移至系统剪贴板。|  
|**复制**|**编辑**|Ctrl+C|将当前选定的文本复制到系统剪贴板。|  
|**粘贴**|**编辑**|Ctrl+V|将文本从系统剪贴板粘贴到当前活动的文本元素中。|  
|**删除**|**编辑**||删除列表中当前选定的元素，如“部署清单”  选项卡上的信任许可证。|  
|**全部关闭**|**窗口**||关闭 MageUI.exe 中当前打开的所有文件。 如果一个或多个文件需要保存，则 MageUI.exe 将提示你对其进行保存。 MageUI.exe 还会提示你为每个未签名或已更改的文件选择一个签名密钥。|  
|**关于**|**帮助**||显示有关 MageUI.exe 的版本和版权信息。|  
  
## <a name="preferences-dialog-box"></a>“首选项”对话框  
 “首选项”  对话框包含下列元素。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**保存时签名**|当你保存修改时提示对文件进行签名。|  
|**使用默认签名证书**|使用在“证书文件”  文本框中输入的密钥对全部文件进行签名。 这样可消除通常在你保存文件并且选择了“保存时签名”  时出现的签名提示。 使用“证书文件”  文本框旁边的省略号 ( **…** ) 按钮选择密钥文件。|  
|摘要算法|指定用来生成依赖项摘要的算法。 值必须为“sha256RSA”或“sha1RSA”。 使用 SHA1 作为默认值。 在应用程序和部署清单中使用。 如果用户在保存清单时提供证书，则使用证书中的算法生成依赖项摘要。|  
  
## <a name="signing-options-dialog-box"></a>“签名选项”对话框  
 首次保存清单或信任许可证，或者更改清单或信任许可证时，会显示“签名选项”  对话框。 仅当选择了“首选项”  对话框中的“保存时签名”  选项时，才会显示该对话框。 在对指定“时间戳 URI”  文本框中的值的清单进行签名时，必须连接到 Internet。  
  
 该对话框包含下列元素。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**使用证书文件签名**|使用文件系统上存储的数字证书对清单进行签名。|  
|**文件**|提供一个可以键入表示证书的 .pfx 文件的路径的区域。|  
|**...**|打开“选择文件”  对话框，以便选择现有的 .pfx 文件。|  
|**新建**|生成一个无法通过证书颁发机构 (CA) 验证的新 .pfx。 要详细了解用于对 ClickOnce 部署进行签名的证书类型，请参阅[受信任的应用程序部署概述](/visualstudio/deployment/trusted-application-deployment-overview)。|  
|**密码**|提供一个可以键入在使用此证书进行签名时所需要的密码的区域。 如果不适用，则可以保留为空白。|  
|**使用存储的证书签名**|显示计算机的证书存储区中存储的可选数字证书的列表。|  
|**时间戳 URI**|显示数字时间戳服务的统一资源定位器 (URI)。 如果数字证书在你部署应用程序的下一个版本之前过期，则为清单加盖时间戳可以让你不必对清单进行重新签名。 有关详细信息，请参阅 [Windows 根证书程序成员](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265983(v=ws.11))以及 [ClickOnce 和 Authenticode](/visualstudio/deployment/clickonce-and-authenticode)。|  
|**不签名**|允许你保存清单，而无需添加数字证书签名。|  
  
## <a name="tab-and-panel-descriptions"></a>选项卡和面板的说明  
 使用 MageUI.exe 打开某个文档时，该文档将显示在自己的选项卡页中。 每个选项卡都包含一组属性面板。 这些面板包含经过分组的文档数据子集。  
  
### <a name="application-manifest-tab"></a>应用程序清单选项卡  
 “应用程序清单”  选项卡显示应用程序清单的内容。 应用程序清单描述了部署中包含的所有文件，以及要在客户端上运行应用程序所需的权限。  
  
 “应用程序清单”  选项卡包含以下选项卡。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**Name**|指定有关此部署的识别信息。|  
|**说明**|指定发布者、产品和支持信息。|  
|**应用程序选项**|指定它是否为浏览器应用程序，以及此清单是否为信任信息的源。|  
|**文件**|指定构成此部署的所有文件。|  
|**所需权限**|指定在客户端上运行应用程序所需的最小权限集。|  
  
### <a name="name-tab"></a>名称选项卡  
 首次创建或打开应用程序清单时，会显示“名称”  选项卡。 它唯一地标识部署，并选择性地指定有效目标平台。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**Name**|必需。 应用程序清单的名称。 通常与文件名相同。|  
|**Version**|必需。 部署的版本号，格式为 *N.N.N.N*。 只有第一个主要内部版本号是必需的。 例如，对于应用程序的 1.0 版，有效值包括 `1`、`1.0`、`1.0.0` 和 `1.0.0.0`。|  
|**处理器**|可选。 此部署可在其上运行的计算机体系结构。 默认值为 `msil`，即 Microsoft 中间语言，它是所有托管程序集的默认格式。 如果在应用程序中对程序集进行了预编译（以使其适用于特定的体系结构），则请更改此字段。 有关预编译的详细信息，请参阅 [Ngen.exe（本机映像生成器）](ngen-exe-native-image-generator.md)。|  
|**区域性**|可选。 应用程序在其中运行的两部分 ISO 国家和地区代码。 默认值为 `neutral`。|  
|**公钥标记**|可选。 已用于对此应用程序清单进行签名的公钥。 如果这是新清单或未签名的清单，则此字段显示为 `Unsigned`。|  
  
### <a name="description-tab"></a>说明选项卡  
 通常在部署清单中提供此信息。 只有在“应用程序选项”  选项卡上选中了“使用应用程序清单信任信息”  复选框时，才能修改这些字段。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**发布者**|负责该应用程序的个人或组织的姓名或名称。 此值用作“开始”菜单文件夹名。|  
|**产品**|完整的产品名称。 如果为部署清单的“部署选项”  选项卡上的“应用程序类型”  元素选择了“本地安装”  ，则此名称将为此应用程序的“开始”  菜单链接和“添加或删除程序”  中显示的名称。|  
|**支持位置**|客户可以从中为应用程序获取帮助和支持的 URL。|  
  
### <a name="application-options-tab"></a>应用程序选项选项卡  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**Windows Presentation Foundation 浏览器应用程序**|指定它是否是在浏览器中作为 XAML 浏览器应用程序 (XBAP) 运行的 WPF 应用程序。|  
|**使用应用程序清单信任信息**|指定此清单是否包含信任信息。|  
  
### <a name="files-tab"></a>文件选项卡  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**应用程序目录**|应用程序的文件驻留在其中的目录。 使用省略号 ( **…** ) 按钮选择此目录。|  
|**填充**|将应用程序目录和子目录中的所有文件添加到应用程序清单。 如果 MageUI.exe 在目录中找到单个可执行文件，它会自动将其标记为入口点，即客户端上启动 ClickOnce 应用程序时执行时的第一个文件。|  
|**应用程序文件**|列出应用程序中的所有文件。 每个文件具有三个可编辑的特性，如下所述。|  
|**文件类型**|文件类型可以是以下四个值之一：<br /><br /> -   无。<br />-   入口点。 应用程序的主要可执行文件。 只能将一个可执行文件标记为入口点。<br />-   数据文件。 向应用程序提供数据的文件（例如 XML 文件）。<br />-   图标文件。 应用程序图标，例如出现在桌面上或应用程序的窗口一角的图标。|  
|**Optional**|不会在初次安装或更新时下载标记为可选的文件，但可能在运行时使用 System.Deployment 按需 API 下载。 有关详细信息，请参见[演练：在设计器中使用 ClickOnce 部署 API 按需下载程序集](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)。|  
|**组**|一组可选的文件的标签。 可以将组标签应用于一组文件，并使用按需 API 下载一批文件（只进行一次 API 调用）。|  
  
### <a name="permissions-required-tab"></a>所需权限选项卡  
 如果需要向应用程序授予比默认授予更多的本地计算机访问权限，请使用“所需权限”  选项卡。 有关详细信息，请参阅[保护 ClickOnce 应用程序](/visualstudio/deployment/securing-clickonce-applications)。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**权限集类型**|在客户端上运行此应用程序所需的最小权限集。 有关这些权限集以及需要的或不需要的权限的说明，请参阅[命名的权限集](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100))。|  
|**详细信息**|为应用程序清单创建用于表示权限集的 XML。 除非充分理解应用程序清单 XML 格式，否则不应手动编辑此 XML。 有关详细信息，请参阅 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)。|  
  
### <a name="deployment-manifest-tab"></a>部署清单选项卡  
 “部署清单”  选项卡包含以下选项卡。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**Name**|指定有关此部署的识别信息。|  
|**说明**|指定发布者、产品和支持信息。|  
|**部署选项**|指定有关部署的其他信息，如应用程序类型和开始位置。|  
|**更新选项**|指定 ClickOnce 应多久检查一次应用程序更新。|  
|**应用程序引用**|指定此部署的应用程序清单。|  
  
### <a name="name-tab"></a>名称选项卡  
 首次创建或打开部署清单时，会显示“名称”  选项卡。 它唯一地标识部署，并选择性地指定有效目标平台。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**Name**|必需。 部署清单的名称。 通常与文件名相同。|  
|**Version**|必需。 部署的版本号，格式为 *N.N.N.N*。 只有第一个主要内部版本号是必需的。 例如，对于应用程序的 1.0 版，有效值包括 `1`、`1.0`、`1.0.0` 和 `1.0.0.0`。|  
|**处理器**|可选。 此部署可在其上运行的计算机体系结构。 默认值为 `msil`，即 Microsoft 中间语言，它是所有托管程序集的默认格式。 如果在应用程序中对程序集进行了编译（以使其适用于特定的体系结构），则请更改此字段。|  
|**区域性**|可选。 应用程序在其中运行的两部分 ISO 国家/地区代码。 默认值为 `neutral`。|  
|**公钥标记**|可选。 已用于对此部署清单进行签名的公钥。 如果这是新清单或未签名的清单，则此字段显示为 `Unsigned`。|  
  
### <a name="description-tab"></a>说明选项卡  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**发布者**|必需。 负责该应用程序的个人或组织的姓名或名称。 此值用作“开始”菜单文件夹名。|  
|**产品**|必需。 完整的产品名称。 如果为“部署选项”  选项卡上的“应用程序类型”  元素选择了“本地安装”  ，则此名称将为此应用程序的“开始”  菜单链接和“添加或删除程序”  中显示的名称。|  
|**支持位置**|可选。 客户可以从中为应用程序获取帮助和支持的 URL。|  
  
### <a name="deployment-options-tab"></a>部署选项选项卡  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**应用程序类型**|可选。 指定此应用程序是将其自身安装到客户端计算机（“本地安装”  ）、联机运行（“仅限联机状态”  ），还是作为在浏览器中运行的 WPF 应用程序（“WPF 浏览器应用程序”  ）。 默认值是“本地安装”  。|  
|**开始位置**|可选。 应用程序应实际从其启动的 URL。 在从 CD 部署应从 Web 进行自我更新的应用程序时非常有用。|  
|**在清单中包括开始位置(ProviderURL)**|可选。 指定 ClickOnce 要检查是否存在应用程序更新的 URL。|  
|**安装后自动运行应用程序**|必需。 指定 ClickOnce 应用程序应在从 URL 初始安装后立即运行。 默认选中此复选框。|  
|**允许向应用程序传递 URL 参数**|必需。 允许通过追加到部署清单 URL 的查询字符串将参数数据传输给 ClickOnce 应用程序。 默认情况下，不选中此复选框。|  
|**使用 .deploy 文件扩展名**|必需。 选中后，应用程序清单中的所有文件都必须具有 .deploy 扩展名。 默认情况下，不选中此复选框。|  
  
### <a name="update-options-tab"></a>更新选项选项卡  
 仅当“名称”  选项卡上的“应用程序类型”  选择框设置为“本地安装”  时，“更新选项”  选项卡才包含此处提及的选项。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**此应用程序应检查更新**|指定 ClickOnce 是否应检查应用程序更新。 如果未选中此复选框，应用程序将不检查更新，除非通过使用 <xref:System.Deployment.Application> 命名空间中的 API 以编程方式进行更新。|  
|**选择应用程序何时应该检查更新**|提供两个更新检查选项：<br /><br /> -   **应用程序启动前**。 在应用程序执行之前执行更新检查。<br />-   **应用程序启动后**。 更新检查在应用程序主窗体初始化后开始，并将在下次启动该应用程序时运行。|  
|**更新检查频率**|确定 ClickOnce 应多久检查一次更新：<br /><br /> -   **每次应用程序运行时检查**。 ClickOnce 在用户每次打开应用时都将执行更新检查。<br />-   检查间隔：  ：选择检查更新之前必须经过的时间间隔和单位（小时、天或周）。|  
|**指定所需的此应用程序的最低版本**|可选。 指定应用程序的特定版本为必需的安装，从而防止用户使用更早版本。|  
|**Version**|如果已选中“指定所需的此应用程序的最低版本”  复选框，则为必需。 提供的版本号的格式必须为 *N.N.N.N*。 只有第一个主要内部版本号是必需的。 例如，对于应用程序的 1.0 版，有效值包括 `1`、`1.0`、`1.0.0` 和 `1.0.0.0`。|  
  
### <a name="application-reference-tab"></a>应用程序引用选项卡  
 “应用程序引用”  选项卡包含与本主题前面所述的“名称”  选项卡相同的字段。 唯一的例外是下面的字段。  
  
|UI 元素|说明|  
|----------------|-----------------|  
|**选择清单**|使你能够选择应用程序清单。 选择应用程序清单后，此页面上的所有其他字段均将进行填充。|  
  
## <a name="see-also"></a>请参阅

- [ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)
- [演练：手动部署 ClickOnce 应用程序](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)
- [Mage.exe（清单生成和编辑工具）](mage-exe-manifest-generation-and-editing-tool.md)
