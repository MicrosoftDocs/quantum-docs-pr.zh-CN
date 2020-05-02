---
title: 使用 Q# + Python 进行开发
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: e1b8a0c68b3ac0c059c6de6e478593321764ff88
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680151"
---
# <a name="develop-with-q--python"></a>使用 Q# + Python 进行开发

安装 QDK 以开发 Python 主机程序以调用 Q # 操作。

1. 先决条件

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器
    - [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)


1. 安装`qsharp`包，这是启用 Q # 和 Python 之间的互操作的 python 包。

    ```bash
    pip install qsharp
    ```

1. 安装 IQ #，Jupyter 和 Python 使用的内核，提供用于编译和执行 Q # 操作的核心功能。

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. 尽管可以在任何 IDE 中将 Q # 与 Python 一起使用，但我们强烈建议对 Q # + Python 应用程序使用 Visual Studio Code （VS Code） IDE。 通过使用 Visual Studio Code 和 QDK Visual Studio Code 扩展，你可以访问更丰富的功能。

    - 安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）
    - [为 VS Code 安装 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

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

        ```bash
        python hello_world.py
        ```

    - 验证输出。 程序应输出以下行：

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * 你还可以使用 Python Jupyter 笔记本编写传统的 Python 程序并从单元格中调用 Q # 操作。 Python 代码只是一个普通的 Python 计划。

## <a name="whats-next"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。
