---
title: '执行无驱动程序和主机语言的 Q # 程序'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706795"
---
# <a name="q-command-line-applications"></a>Q # 命令行应用程序

Q # 程序可以自行执行，而不能在 c #、F # 或 Python 等主机语言中使用驱动程序。

## <a name="pre-requisites"></a>先决条件

- [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安装

尽管可以在任何 IDE 中生成 Q # 命令行应用程序，但我们强烈建议对 Q # 应用程序使用 Visual Studio Code （VS Code）或 Visual Studio IDE。 通过使用 VS Code 或 Visual Studio 和 QDK Visual Studio Code 扩展，你可以访问更丰富的功能。

- 安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）
- [为 VS Code 或安装 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，启用了 .NET Core 跨平台开发工作负载。
- 下载并安装[Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>使用 VS Code 与 Q # 进行开发

安装量子项目模板：

- 中转到 "**视图** -> "**命令面板**
- 选择**Q #：安装项目模板**

现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。
- 创建新项目：
  - 中转到 "**视图** -> "**命令面板**
  - 选择**Q #：创建新项目**
  - 选择**独立控制台应用程序**
  - 导航到要在其中创建应用程序的文件系统上的位置
  - 创建项目后，单击“打开新项目...”**** 按钮
        
- 检查项目
  - 应会看到名`Program.qs`为 "创建" 的文件，该文件是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。

- 运行应用程序：
  - 中转到**终端** -> **新终端**
  - 输入 `dotnet run`
  - 应在输出窗口 `Hello quantum world!` 中看到以下文本


> [!NOTE]
> * Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。 如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。

## <a name="develop-with-q-using-visual-studio"></a>使用 Visual Studio 通过 Q # 进行开发

通过创建 `Hello World` 应用程序来验证安装

- 创建新的 Q# 应用程序
  - 中转到 "**文件** -> " "**新建** -> **项目**"
  - 在搜索框中键入 `Q#`
  - 选择“Q# 应用程序”****
  - 选择 **“下一步”**。
  - 为应用程序选择名称和位置
  - 选择**创建**

- 检查项目
  - 应会看到已创建一个名`Program.qs`为的文件，这是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。

- 运行应用程序
  - 选择 "**调试** -> **开始" （不调试**）
  - 应该会看到打印到控制台窗口的文本 `Hello quantum world!`。

> [!NOTE]
> * 如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。  


## <a name="whats-next"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。
