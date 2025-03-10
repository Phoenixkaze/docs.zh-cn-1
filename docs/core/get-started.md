---
title: .NET Core 入门
description: 查找相关资源，了解如何在 Windows、Linux 和 macOS 上生成 .NET Core 应用程序。
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 78066f2904f6a874b71165e4fe1769b6b778ae41
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428867"
---
# <a name="get-started-with-net-core"></a>.NET Core 入门

本文提供 .NET Core 入门的相关信息。 可在 Windows、Linux 和 macOS 上安装 .NET Core。 你可在最喜欢的文本编辑器中编写代码并生成跨平台的库和应用程序。 

如果不确定 .NET Core 是什么或其与其他 .NET 技术的关系，请首先参阅 [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet)（.NET 是什么）概述。 简单地说，.NET Core 是一个跨平台的开放源代码 .NET 实现。

## <a name="create-an-application"></a>创建应用程序

首先，在计算机上下载并安装 [.NET Core SDK](https://dotnet.microsoft.com/download)。

然后，打开某一终端，如 PowerShell、命令提示符或 Bash    。 键入以下 `dotnet` 命令以创建并运行 C# 应用程序：

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

您应看到以下输出：

```console
Hello World!
```

祝贺你！ 现已创建了一个简单的 .NET Core 应用程序。 还可以使用 [Visual Studio Code](tutorials/with-visual-studio-code.md)、[Visual Studio](tutorials/with-visual-studio.md)（仅限 Windows）或 [Visual Studio for Mac](tutorials/using-on-mac-vs.md)（仅限 macOS）来创建 .NET Core 应用程序。

## <a name="tutorials"></a>教程

可以通过以下分步教程着手开发 .NET Core 应用程序。

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

- [使用 Visual Studio 2017 生成 C# .NET Core“Hello World”应用程序。](./tutorials/with-visual-studio.md)
- [使用 Visual Studio 2017 生成 C# .NET Core 类库。](./tutorials/library-with-visual-studio.md)
- [使用 Visual Studio 2017 生成 Visual Basic .NET Core“Hello World”应用程序。](./tutorials/vb-with-visual-studio.md)
- [使用 Visual Studio 2017 生成 Visual Basic 和 .NET Core 类库。](./tutorials/vb-library-with-visual-studio.md)  
- 观看视频，了解[如何安装和使用 Visual Studio Code 和 .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)。
- 观看视频，了解[如何安装和使用 Visual Studio 2017 和 .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/)。
- [使用命令行实现 .NET Core 入门。](tutorials/using-with-xplat-cli.md)

请参阅 [.NET Core 依赖项和要求](install/dependencies.md?tabs=netcore30&pivots=os-windows)一文，以获取支持的 Windows 版本列表。

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

可以通过以下分步教程着手开发 .NET Core 应用程序：

- [使用命令行实现 .NET Core 入门。](tutorials/using-with-xplat-cli.md)
- 观看视频：[在 Ubuntu 上使用 C# 和 .NET Core 实现 Visual Studio Code 入门](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)。

请参阅 [ 依赖项和要求](install/dependencies.md?tabs=netcore30&pivots=os-linux)一文，以获取支持的 Linux 发行版和版本列表。

# <a name="macostabmacos"></a>[macOS](#tab/macos)

可以通过以下分步教程着手开发 .NET Core 应用程序：

- 观看视频：[在 macOS 上使用 C# 和 .NET Core 实现 Visual Studio Code 入门](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)。
- [使用 Visual Studio Code 在 macOS 上实现 .NET Core 入门。](tutorials/using-on-macos.md)
- [使用命令行实现 .NET Core 入门。](tutorials/using-with-xplat-cli.md)
- [借助 Visual Studio for Mac 在 macOS 上实现 .NET Core 入门。](tutorials/using-on-mac-vs.md)
- [使用 Visual Studio for Mac 在 macOS 上构建完整的 .NET Core 解决方案。](tutorials/using-on-mac-vs-full-solution.md)

请参阅 [ 依赖项和要求](install/dependencies.md?tabs=netcore30&pivots=os-macos)一文，以获取支持的 OS X / macOS 版本列表。

---
