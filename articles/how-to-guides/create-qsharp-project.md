---
title: '了解如何使用量程开发工具包（QDK）创建 Q # 项目'
description: '使用所选开发环境中的 QDK 和 Q # 初始化项目以进行量程开发'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: c093284f1ea33b72d4d264992b0ba6bf6bc72782
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036434"
---
# <a name="create-a-q-project-in-your-development-environment"></a>在开发环境中创建 Q # 项目

了解如何使用 QDK 创建 Q # 项目。

Q # 项目包含包含量程代码的 Q # 文件，以及运行量程程序的主机程序。 可以在 .NET 语言（如C#）中或在 Python 中编写宿主程序。 还可以使用 IQ # 内核在 Jupyter 笔记本中运行 Q # 代码。

从以下部分选择你的开发环境和语言：

* [Python](#create-a-python-project)
* [Q # Jupyter 笔记本](#create-a-q-jupyter-notebook-project)
* [C#Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#与 VS Code](#create-a-c-project-using-vs-code)
* [C#用命令行](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>创建 Python 项目

1. 先决条件

     * 安装[适用于 Python 的量程开发工具包](xref:microsoft.quantum.install.python)

1. 为项目创建一个文件夹，并导航到该文件夹

1. 创建一个名为 `Operation.qs`的 Q # 文件，并向其添加 Q # 代码。 例如：

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. 创建名为 `host.py` 的 python 主机文件，以调用 Q # 操作。 例如：

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. 运行该程序：

    ```bash
    python host.py
    ```

1. 验证输出。 程序应输出以下行：

    ```bash
    Hello from quantum world!
    0
    ```

现在，你可以继续开发量程计划。

## <a name="create-a-q-jupyter-notebook-project"></a>创建 Q # Jupyter Notebook 项目

1. 先决条件

    * 安装[适用于 Jupyter 笔记本的量程开发工具包](xref:microsoft.quantum.install.jupyter)

1. 运行以下命令以启动 Notebook 服务器：

    ```bash
    jupyter notebook
    ```

1. 浏览到命令行上显示的 URL。 例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. 浏览器中将出现一个 Jupyter 页。 在 "**文件**" 选项卡上，选择 "**新建** > **Q #** " 以使用 q # 内核创建 Jupyter 笔记本。 将以下代码添加到第一个笔记本单元：

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. 选择**单元格** > **运行单元格**以运行笔记本。 单元输出中会出现 `SayHello`：

    ![包含 Q# 代码的 Jupyter 笔记本单元格](~/media/install-guide-jupyter.png)

    在 Jupyter 笔记本中运行时，将编译 Q # 代码，然后笔记本将输出找到的操作的名称。

1. 在新单元格中，模拟执行刚刚使用 `%simulate` magic 创建的量子计算机操作：

    ![包含 %simulate magic 的 Jupyter 笔记本单元格](~/media/install-guide-jupyter-simulate.png)

    应会看到在屏幕上显示的消息以及所调用操作的结果（在本例中为空）。

你现在可以添加其他 Q # 操作来继续进行量程开发。

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>使用 Visual C# Studio 在 Windows 上创建项目

1. 先决条件

    * 安装[适用于 Visual Studio 的量程开发工具包扩展](xref:microsoft.quantum.install.cs)

1. 创建新的 Q# 应用程序

    * 转到“文件” **“新建”** “项目” ->  -> 
    * 在搜索框中键入 `Q#`
    * 选择“Q# 应用程序”
    * 选择 **“下一步”** 。
    * 为应用程序选择名称和位置
    * 选择“创建”

1. 检查项目

    应该会看到已创建两个文件：`Driver.cs`，它是 C# 主机应用程序；以及 `Operation.qs`，它是定义将消息打印到控制台的简单操作的 Q# 程序。

1. 运行应用程序

    * 选择“调试” -> “在不调试的情况下启动”
    * 应该会看到打印到控制台窗口的文本 `Hello quantum world!`。

你现在可以使用 Visual Studio 继续进行量程开发

> [!NOTE]
> * 如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。  

## <a name="create-a-c-project-using-vs-code"></a>使用 VS Code C#创建项目

1. 先决条件

    * 安装[VS Code 的量程开发工具包扩展](xref:microsoft.quantum.install.cs)

1. 创建新项目：

    * 转到“视图” **“命令面板”**  -> 
    * 选择**Q #：创建新项目**
    * 选择**独立控制台应用程序**
    * 导航到要在其中创建应用程序的文件系统上的位置
    * 创建项目后，单击“打开新项目...”按钮

1. 运行应用程序：

    * 中转到**终端** -> **新终端**
    * 输入 `dotnet run`
    * 应在输出窗口 `Hello quantum world!` 中看到以下文本

你现在可以使用 Visual Studio Code 继续进行量程开发。

> [!NOTE]
> * Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。 如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>使用 `dotnet` C#命令行工具创建项目

1. 先决条件

    * 安装[命令行的量程开发工具包](xref:microsoft.quantum.install.cs)

1. 创建新应用程序

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. 导航到新的应用程序目录

    ```bash
    cd <project name>
    ```

    应该会看到已创建两个文件，以及应用程序的项目文件：Q# 文件 (`Operation.qs`) 和 C# 主机文件 (`Driver.cs`)。

1. 运行应用程序

    ```dotnetcli
    dotnet run
    ```

    应该会看到以下输出：`Hello quantum world!`

现在，使用命令行工具继续进行量程开发。

## <a name="whats-next"></a>后续步骤

现在您已在首选环境中创建了一个项目，您可以继续进行量程开发。
