---
title: 使用 Q# 和 Python 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 4d148435f01d975e690828dd02335758fc71dfe4
ms.sourcegitcommit: 2f4c637e194dc2b5d18539469ed37444e2800199
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "87436545"
---
# <a name="develop-with-q-and-python"></a>使用 Q# 和 Python 进行开发

安装用于开发 Python 主机程序的 QDK 以调用 Q# 操作。

## <a name="install-the-qsharp-python-package"></a>安装 `qsharp` Python 包

### <a name="install-using-conda-recommended"></a>[使用 conda 进行安装（推荐）](#tab/tabid-conda)

1. 安装 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。 **注意：** 需要安装 64 位。

1. 打开 Anaconda 提示。

   - 如果更想要使用 PowerShell 或 pwsh：请打开 shell，运行 `conda init powershell`，然后关闭再重新打开 shell。

1. 通过运行以下命令，使用所需的包（包括 Jupyter Notebook 和 IQ#）来创建和激活新的 conda 环境 `qsharp-env`：

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. 从同一终端运行 `python -c "import qsharp"` 来验证安装项，并用所需的 QDK 组件填充本地包缓存。

### <a name="install-using-net-cli-and-pip-advanced"></a>[使用 .NET CLI 和 pip 进行安装（高级）](#tab/tabid-dotnetcli)

1. 先决条件：

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. 安装 `qsharp` 包，这是一个可实现 Q# 和 Python 之间互操作的 Python 包。

    ```
    pip install qsharp
    ```

1. 安装 IQ#，它是 Jupyter 和 Python 使用的内核，提供用于编译和执行 Q# 操作的核心功能。

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

就这么简单！ 你现在有了 `qsharp` Python 包和 Jupyter 的 IQ# 内核，它为用 Python 来编译和执行 Q# 操作提供了核心功能，你还可通过它使用 Q# Jupyter Notebooks。

## <a name="choose-your-ide"></a>选择 IDE

虽然可以在任何 IDE 中结合使用 Q# 与 Python，但我们强烈建议为 Q# + Python 应用程序使用 Visual Studio Code (VS Code) IDE。 通过 QDK Visual Studio Code 扩展，你可获得更丰富的功能，例如警告、语法突出显示和项目模板等。

如果想要使用 VS Code：

- 安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）。
- 安装[适用于 VS Code 的 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

如果想要使用其他编辑器，则上述说明都已全部设置好。

## <a name="write-your-first-q-program"></a>编写你的第一个 Q# 程序

你现可通过编写和执行简单的 Q# 程序来验证 `qsharp` Python 包安装项。

1. 通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. 在 `Operation.qs` 所在的文件夹中，创建一个名为 `host.py` 的 Python 程序来模拟 Q# `SampleQuantumRandomNumberGenerator()` 操作：

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. 从在安装期间创建的环境（即安装 `qsharp` 的 conda 或 Python 环境），请运行以下程序：

    ```
    python host.py
    ```

1. 应会看到所调用的操作的结果。 在本例中，由于操作会生成一个随机结果，因此你将看到屏幕上输出 `0` 或 `1`。 如果重复执行该程序，则每个结果显示的时间大约减半。

> [!NOTE]
> * Python 代码只是普通的 Python 程序。 你可使用任何 Python 环境（包括基于 Python 的 Jupyter Notebooks）来编写 Python 程序和调用 Q# 操作。 Python 程序可从 Python 代码本身所在的文件夹中的任意 .qs 文件导入 Q# 操作。

## <a name="next-steps"></a>后续步骤

在首选环境中安装量子开发工具包之后，可按照本教程编写并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
