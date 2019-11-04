---
title: 了解如何安装 Microsoft Quantum 开发工具包 (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 090cf98612c6c549c733e54f9dcbf74442b30fbd
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442278"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>安装 Microsoft Quantum 开发工具包 (QDK)

了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。 QDK 包括：

- Q# 编程语言
- 在 Q# 中对复杂功能进行抽象化的一组库
- 运行以 Q# 编写的量子操作的主机应用程序（以 Python 或 .NET 语言编写）
- 用于促进开发的工具

根据所选的开发环境，有不同的安装步骤。 从以下部分中选择环境。

## <a name="develop-with-python"></a>使用 Python 进行开发

使用 Python 的 qsharp 包可以轻松地从 Python 内模拟 Q# 操作和函数。 IQ# （发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的扩展，它提供用于编译和模拟 Q# 操作的核心功能。

1. 先决条件

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器
    - [.NET Core SDK 3.0 或更高版本](https://www.microsoft.com/net/download)

1. 安装 `iqsharp` 包

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 安装 `qsharp` 包

    ```bash
    pip install qsharp
    ```

1. 通过创建 `Hello World` 应用程序来验证安装

    - 通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - 创建名为 `hello_world.py` 的 Python 程序来调用 Q# `SayHello()` 操作：

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - 运行该程序：

        ```bash
        python hello_world.py
        ```

    - 验证输出。 程序应输出以下行：

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>使用 Jupyter Notebook 进行开发

Jupyter 笔记本包含非常受人喜爱的学术设置、科学实验室和基于联机的协作编程功能，提供就地代码执行（现在包括 Q# 代码）以及说明、注释和其他内容。  下面是开始创建自己的 Q# 笔记本时需要执行的操作。

IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。


1. 先决条件

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [Jupyter 笔记本](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.0 或更高版本](https://www.microsoft.com/net/download)

1. 安装 `iqsharp` 包

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 通过创建 `Hello World` 应用程序来验证安装

    - 运行以下命令以启动 Notebook 服务器：

        ```bash
        jupyter notebook
        ```

    - 浏览到命令行上显示的 URL。 例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - 使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个 Notebook 单元格：

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - 运行以下 Notebook 单元格：

        ![包含 Q# 代码的 Jupyter 笔记本单元格](~/media/install-guide-jupyter.png)

        应在单元格的输出中看到 `SayHello`。 在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且 Notebook 将输出找到的操作的名称。


    - 在新单元格中，模拟执行刚刚使用 `%simulate` magic 创建的量子计算机操作：

        ![包含 %simulate magic 的 Jupyter 笔记本单元格](~/media/install-guide-jupyter-simulate.png)

        应会看到在屏幕上显示的消息以及所调用操作的结果（在本例中为空）。


## <a name="develop-with-c-on-windows-using-visual-studio"></a>在 Windows 上使用 C# 进行开发，使用 Visual Studio

Visual Studio 提供了用于开发 Q# 程序的丰富环境，并且提供了代码完成和语法突出显示等强大功能，以便指导开发人员构建其应用程序。  Q# Visual Studio 扩展包含用于 Q# 文件和项目的模板，以及语法突出显示和 IntelliSense 支持。


1. 先决条件

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，启用了 .NET Core 跨平台开发工作负载。

1. 安装 Q# Visual Studio 扩展

    - 下载 [Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - 将扩展添加到 Visual Studio

1. 通过创建 `Hello World` 应用程序来验证安装

    - 创建新的 Q# 应用程序

        - 转到“文件” -> “新建” -> “项目”   
        - 在搜索框中键入 `Q#`
        - 选择“Q# 应用程序” 
        - 选择“下一步” 
        - 为应用程序选择名称和位置
        - 选择“创建” 

    - 检查项目

        应该会看到已创建两个文件：`Driver.cs`，它是 C# 主机应用程序；以及 `Operation.qs`，它是定义将消息打印到控制台的简单操作的 Q# 程序。

    - 运行应用程序

        - 选择“调试”   -> “在不调试的情况下启动” 
        - 应该会看到打印到控制台窗口的文本 `Hello quantum world!`。

> [!NOTE]
> * 如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。  

## <a name="develop-with-c-using-visual-studio-code"></a>使用 Visual Studio Code 以 C# 进行开发

Visual Studio (VS Code) 提供了用于跨许多计算机环境（包括 Windows、Linux 和 Mac）开发 Q# 程序的丰富环境，并且提供了代码完成和语法突出显示等强大功能，以便指导开发人员构建其应用程序。  Q# VS Code 扩展包含语法突出显示和 Q# 代码片段。

Visual Studio (VS Code) 提供了用于跨许多计算机环境（包括 Windows、Linux 和 Mac）开发 Q# 程序的丰富环境，并且提供了代码完成和语法突出显示等强大功能，以便指导开发人员构建其应用程序。  Q# VS Code 扩展包含语法突出显示和 Q# 代码片段。

1. 先决条件

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.0 或更高版本](https://www.microsoft.com/net/download)

1. 安装量子 VS Code 扩展

    - 安装 [VS Code 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. 安装量子项目模板：

   - 转到“视图” -> “命令面板”  
   - 选择  “Q#: 安装项目模板”

    现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。

1. 通过创建 `Hello World` 应用程序来验证安装

    - 创建新项目：

        - 转到“视图” -> “命令面板”  
        - 选择  “Q#: 创建新项目”
        - 导航到要在其中创建应用程序的文件系统上的位置
        - 创建项目后，单击“打开新项目...”  按钮

    - 运行应用程序：

        - 转到“调试”   -> “在不调试的情况下启动” 
        - 应在输出窗口 `Hello quantum world!` 中看到以下文本

> [!NOTE]
> * > * Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。 如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>使用 C# 进行开发，使用 `dotnet` 命令行工具

当然，只需安装 .NET Core SDK 和 QDK 项目模板，就可以从命令行生成和运行 Q# 程序。 

1. 先决条件

    - [.NET Core SDK 3.0 或更高版本](https://www.microsoft.com/net/download)

1. 安装适用于 .NET 的量子项目模板

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。

1. 通过创建 `Hello World` 应用程序来验证安装

    - 创建新应用程序

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - 导航到新的应用程序目录

       ```bash
       cd runSayHello
       ```

    应该会看到已创建两个文件，以及应用程序的项目文件：Q# 文件 (`Operation.qs`) 和 C# 主机文件 (`Driver.cs`)。

    - 运行应用程序

        ```bash
        dotnet run
        ```

        应该会看到以下输出：`Hello quantum world!`

## <a name="whats-next"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。
