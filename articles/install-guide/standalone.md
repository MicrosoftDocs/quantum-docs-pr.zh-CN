---
title: '用 Q # 命令行应用程序进行开发'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630262"
---
# <a name="develop-with-q-command-line-applications"></a>用 Q # 命令行应用程序进行开发

Q # 程序可以自行执行，而不能在 c #、F # 或 Python 等主机语言中使用驱动程序。

## <a name="prerequisites"></a>先决条件

- [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安装

尽管可以在任何 IDE 中生成 Q # 命令行应用程序，但我们还是建议为 Q # 应用程序使用 Visual Studio Code （VS Code）或 Visual Studio IDE。 使用这些工具进行开发可提供对丰富功能的访问权限。

配置 VS Code：

1. 下载并安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）。
2. 安装[MICROSOFT QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

若要配置 Visual Studio：

1. 下载并安装[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更高版本，并启用 .net Core 跨平台开发工作负荷。
2. 下载并安装[MICROSOFT QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。


## <a name="develop-with-q-using-vs-code"></a>使用 VS Code 与 Q # 进行开发

安装 Q # 项目模板：

1. 打开 VS Code。
2. 单击 "**查看**" "  ->  **命令面板**"。
3. 选择 " **Q #：安装项目模板**"。

如果已**成功安装项目模板**，则可以将 QDK 用于自己的应用程序和库。

创建新项目：

1. 单击 "**查看**" "  ->  **命令面板**"，然后选择 " **Q #：创建新项目**"。
2. 单击 "**独立控制台应用程序**"。
3. 导航到要保存项目的位置，然后单击 "**创建项目**"。
4. 成功创建项目后，单击右下方的 "**打开新项目 ...** "。
        
检查项目。 应该会看到一个名为的源文件，该文件 `Program.qs` 是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。

运行应用程序：
1. 单击 "**终端**  ->  **新终端**"。
2. 在终端提示符下，输入 `dotnet run` 。
3. 应在输出窗口 `Hello quantum world!` 中看到以下文本


> [!NOTE]
> VS Code Q # 扩展当前不支持具有多个根文件夹的工作区。 如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。

## <a name="develop-with-q-using-visual-studio"></a>使用 Visual Studio 通过 Q # 进行开发

通过创建 Q # 应用程序来验证你的 Visual Studio 安装 `Hello World` 。

若要创建新的 Q # 应用程序：
1. 打开 Visual Studio，然后单击 "**文件**" "  ->  **新建**  ->  **项目**"。
2. `Q#`在搜索框中键入，选择 " **Q # 应用程序**"，然后单击 "**下一步**"。
3. 输入应用程序的名称和位置，然后单击 "**创建**"。


检查项目。 应该会看到一个名为的源文件，该文件 `Program.qs` 是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。

运行应用程序：
1. 选择 "**调试**开始" （  ->  **不调试**）。
2. 应该会看到打印到控制台窗口的文本 `Hello quantum world!`。

> [!NOTE]
> 如果一个 Visual Studio 解决方案中有多个项目，则解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其某个子文件夹中。  


## <a name="next-steps"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
