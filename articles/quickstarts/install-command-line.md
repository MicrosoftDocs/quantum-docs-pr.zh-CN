---
title: 开发 Q# 命令行应用程序
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274040"
---
# <a name="develop-with-q-command-line-applications"></a>开发 Q# 命令行应用程序

Q# 程序可以自己执行，而无需采用 C#、F# 或 Python 等主机语言的驱动程序。

## <a name="prerequisites"></a>先决条件

- [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安装

尽管可以在任何 IDE 中生成 Q# 命令行应用程序，但我们还是建议为 Q# 应用程序使用 Visual Studio Code (VS Code) 或 Visual Studio IDE。 这些工具为开发提供丰富的功能。

配置 VS Code：

1. 下载并安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）。
2. 安装[适用于 VS Code 的 Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

配置 Visual Studio:

1. 下载并安装 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更高版本，并启用 .NET Core 跨平台开发工作负载。
2. 下载并安装 [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。


## <a name="develop-with-q-using-vs-code"></a>使用 VS Code 和 Q# 进行开发

安装 Q# 项目模板：

1. 打开 VS Code。
2. 单击“查看” -> “命令面板” 。
3. 选择安装项目模板。

如果显示“已成功安装项目模板”，可以为自己的应用程序和库使用 QDK。

创建新项目：

1. 单击“查看” -> “命令面板”，然后选择 Q#  **：** Create New Project”。
2. 单击“独立控制台应用程序”。
3. 导航到项目的保存位置，然后单击“创建项目”。
4. 成功创建项目后，单击右下方的“打开新项目…”。
        
检查项目。 你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。

运行应用程序：
1. 单击“终端” -> “新终端” 。
2. 在终端提示符下，输入 `dotnet run`。
3. 应在输出窗口 `Hello quantum world!` 中看到以下文本


> [!NOTE]
> VS Code Q# 扩展当前不支持具有多个根文件夹的工作区。 如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。

## <a name="develop-with-q-using-visual-studio"></a>使用 Visual Studio 和 Q# 进行开发

创建 Q# `Hello World` 应用程序，验证 Visual Studio 安装。

创建新的 Q# 应用程序：
1. 打开 Visual Studio，单击“文件” -> “新建” -> “项目”  。
2. 在“搜索”框中键入 `Q#`，选择“Q# 应用程序”，然后单击“下一步” 。
3. 输入应用程序的“名称”和“位置”，然后单击“创建”。


检查项目。 你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。

运行应用程序：
1. 选择“调试” -> “在不调试的情况下启动”。
2. 应该会看到打印到控制台窗口的文本 `Hello quantum world!`。

> [!NOTE]
> 如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。  


## <a name="next-steps"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
