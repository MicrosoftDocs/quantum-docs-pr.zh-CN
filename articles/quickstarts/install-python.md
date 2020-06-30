---
title: 使用 Q# 和 Python 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274021"
---
# <a name="develop-with-q-and-python"></a>使用 Q# 和 Python 进行开发

安装用于开发 Python 主机程序的 QDK 以调用 Q# 操作。

1. 先决条件

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
  
1. 虽然可以在任何 IDE 中结合使用 Q# 与 Python，但我们强烈建议为 Q# + Python 应用程序使用 Visual Studio Code (VS Code) IDE。 使用 Visual Studio Code 和 QDK Visual Studio Code 扩展可访问更丰富的功能。

    - 安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）
    - 安装[适用于 VS Code 的 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

1. 通过创建 `Hello World` 应用程序来验证安装

    - 通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
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

        ```
        python hello_world.py
        ```

    - 验证输出。 程序应输出以下行：

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * 还可以使用 Python Jupyter 笔记本编写经典 Python 程序并从单元格中调用 Q# 操作。 Python 代码只是普通的 Python 程序。

## <a name="next-steps"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
