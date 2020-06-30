---
title: 使用 Q# Jupyter Notebook 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274032"
---
# <a name="develop-with-q-jupyter-notebooks"></a>使用 Q# Jupyter Notebook 进行开发

在 Q# Jupyter 笔记本上安装用于开发 Q# 操作的 QDK。

Jupyter Notebook 支持在包含说明、注释和其他内容的情况下就地执行代码。 此环境非常适合编写包含嵌入式说明的 Q# 代码或量子计算交互式教程。 下面是开始创建自己的 Q# 笔记本时需要执行的操作。

IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。

> [!NOTE]
> * 在 Q# Jupyter 笔记本中，只能运行 Q# 代码，不能从外部主机程序（例如 Python 或 C# 文件）调用操作。 如果你的目标是将外部传统主机程序与量子程序结合，则此环境不适合。

1. 先决条件

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [Jupyter 笔记本](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. 安装 `iqsharp` 包

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > 如果在 `dotnet iqsharp install` 步骤中遇到错误，请打开新的终端窗口，然后重试。
    > 如果仍有问题，请尝试查找安装的 `dotnet-iqsharp` 工具（在 Windows 上为 `dotnet-iqsharp.exe`）并运行：
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > 其中 `/path/to/dotnet-iqsharp` 应替换为文件系统中 `dotnet-iqsharp` 工具的绝对路径。
    > 通常，该工具在用户配置文件文件夹中的 `.dotnet/tools` 下。

1. 通过创建 `Hello World` 应用程序来验证安装

    - 运行以下命令以启动 Notebook 服务器：

        ```
        jupyter notebook
        ```

    - 若要打开 Jupyter Notebook，请复制命令行提供的 URL 并将其粘贴到浏览器中。

    - 使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个 Notebook 单元格：

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - 运行以下 Notebook 单元格：

        ![包含 Q# 代码的 Jupyter Notebook 单元格](~/media/install-guide-jupyter.png)

        应在单元格的输出中看到 `SayHello`。 在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且 Notebook 将输出找到的操作的名称。


    - 在新单元格中，使用 `%simulate` 命令执行刚刚创建的操作（在模拟器中）：

        ![包含 %simulate magic 的 Jupyter Notebook 单元格](~/media/install-guide-jupyter-simulate.png)

        你应会看到屏幕上显示的消息以及所调用操作的结果（在本例中，我们会看到空的元组 `()`，因为操作只返回 `Unit` 类型）。

## <a name="next-steps"></a>后续步骤

现在，你已安装适用于 Q# Jupyter Notebook 的 QDK，接下来可以在 Jupyter Notebook 环境中直接编写 Q# 代码，从而完成并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。

要了解更多关于使用 Q# Jupyter Notebook 可以执行的操作的示例，请参阅：
- [Q# 和 Jupyter Notebook 简介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。 这篇文章中介绍了 Q# Jupyter Notebook，演示了如何在此环境中使用 Q#。
- [Quantum Katas](xref:microsoft.quantum.overview.katas) 是一系列采用 Q# Jupyter Notebook 形式的可自定进度的开放元代码教程和编程练习。 可以先从 [Quantum Katas 教程笔记本](https://github.com/microsoft/QuantumKatas#tutorial-topics)开始。 Quantum Katas 的目标是同时教授量子计算和 Q# 编程的要素。 它们很好地演示了可以使用 Q# Jupyter Notebook 创建哪种内容。
