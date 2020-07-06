---
title: 使用 Q# Jupyter Notebook 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 8a878e8f930f4b898f4de35751e4a39cc8716cec
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884222"
---
# <a name="develop-with-q-jupyter-notebooks"></a>使用 Q# Jupyter Notebook 进行开发

在 Q# Jupyter 笔记本上安装用于开发 Q# 操作的 QDK。

Jupyter Notebook 支持在包含说明、注释和其他内容的情况下就地执行代码。 此环境非常适合编写包含嵌入式说明的 Q# 代码或量子计算交互式教程。 下面是开始创建自己的 Q# 笔记本时需要执行的操作。

> [!NOTE]
> * 在 Q# Jupyter Notebooks 中，只能运行 Q# 代码，不能从外部主机程序（例如 Python 或 C# 文件）调用操作。 如果你的目标是将外部传统主机程序与量子程序结合，则此环境不适合。

## <a name="install-the-iq-jupyter-kernel"></a>安装 IQ# Jupyter 内核

IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。

### <a name="install-using-conda-recommended"></a>[使用 conda 进行安装（推荐）](#tab/tabid-conda)

1. 安装 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。

1. 打开 Anaconda 提示。

   - 如果更想要使用 PowerShell 或 pwsh：请打开 shell，运行 `conda init powershell`，然后关闭再重新打开 shell。

1. 通过运行以下命令，使用所需的包（包括 Jupyter Notebook 和 IQ#）来创建和激活新的 conda 环境 `qsharp-env`：

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. 从同一终端运行 `python -c "import qsharp"` 来验证安装项，并用所需的 QDK 组件填充本地包缓存。

### <a name="install-using-net-cli-advanced"></a>[使用 .NET CLI 进行安装（高级）](#tab/tabid-dotnetcli)

1. 先决条件：

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [Jupyter 笔记本](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. 安装 `Microsoft.Quantum.IQSharp` 包。

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
    
***

就这么简单！ 你现在有了 Jupyter 的 IQ# 内核，它为用 Q# 来编译和执行 Q# 操作提供了核心功能。

## <a name="create-your-first-q-notebook"></a>创建你的第一个 Q# 笔记本

你现可通过编写和执行简单的 Q# 操作来验证 Q# Jupyter Notebook 安装项。

1. 从在安装期间创建的环境（即创建的 conda 环境或安装了 Jupyter 的 Python 环境），运行以下命令来启动 Jupyter Notebook 服务器：

    ```
    jupyter notebook
    ```

    - 如果 Jupyter Notebook 未在浏览器中自动打开，请复制命令行提供的 URL 并将其粘贴到浏览器中。

1. 选择“新建”→“Q#”来使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个笔记本单元格：

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. 运行以下笔记本单元格：

    ![包含 Q# 代码的 Jupyter Notebook 单元格](~/media/install-guide-jupyter.png)

    应在单元格的输出中看到 `SampleQuantumRandomNumberGenerator`。 在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且单元格将输出找到的所有操作的名称。

1. 在新单元格中，使用 `%simulate` 命令执行刚刚创建的操作（在模拟器中）：

    ![包含 %simulate magic 的 Jupyter Notebook 单元格](~/media/install-guide-jupyter-simulate.png)

    应会看到所调用的操作的结果。 在本例中，由于操作会生成一个随机结果，因此你将看到屏幕上输出 `Zero` 或 `One`。 如果重复执行该单元格，则每个结果显示的时间大约减半。

## <a name="next-steps"></a>后续步骤

你现已安装适用于 Q# Jupyter Notebooks 的 QDK，接下来可在 Jupyter Notebook 环境中直接编写 Q# 代码，从而完成并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。

要了解更多关于使用 Q# Jupyter Notebook 可以执行的操作的示例，请参阅：

- [Q# 和 Jupyter Notebook 简介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。 你将在这里找到一个 Q# Jupyter Notebook，其中更详细地演示了如何在 Jupyter 环境中使用 Q#。
- [Quantum Katas](xref:microsoft.quantum.overview.katas) 是一系列采用 Q# Jupyter Notebook 形式的可自定进度的开放元代码教程和编程练习。 可以先从 [Quantum Katas 教程笔记本](https://github.com/microsoft/QuantumKatas#tutorial-topics)开始。 Quantum Katas 的目标是同时教授量子计算和 Q# 编程的要素。 它们很好地演示了可以使用 Q# Jupyter Notebook 创建哪种内容。
