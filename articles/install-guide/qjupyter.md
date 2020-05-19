---
title: '用 Q # Jupyter 笔记本进行开发'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551033"
---
# <a name="develop-with-q-jupyter-notebooks"></a>用 Q # Jupyter 笔记本进行开发

在 Q # Jupyter 笔记本上安装用于开发 Q # 操作的 QDK。

Jupyter 笔记本允许就地执行的代码与说明、注释和其他内容。 此环境非常适合用于编写带有嵌入的解释或量子计算交互式教程的 Q # 代码。 下面是开始创建自己的 Q# 笔记本时需要执行的操作。

IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。

> [!NOTE]
> * 在 Q # Jupyter 笔记本中，只能运行 Q # 代码，不能从外部主机程序（例如 Python 或 c # 文件）中调用操作。 如果你的目标是将外部传统主机程序与量程计划结合使用，则此环境不适合。

1. 先决条件

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3。1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

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

    - 若要打开 Jupyter 笔记本，请复制命令行提供的 URL 并将其粘贴到浏览器中。

    - 使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个 Notebook 单元格：

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - 运行以下 Notebook 单元格：

        ![包含 Q# 代码的 Jupyter 笔记本单元格](~/media/install-guide-jupyter.png)

        应在单元格的输出中看到 `SayHello`。 在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且 Notebook 将输出找到的操作的名称。


    - 在新单元中，使用命令执行你刚刚在模拟器中创建的操作 `%simulate` ：

        ![包含 %simulate magic 的 Jupyter 笔记本单元格](~/media/install-guide-jupyter-simulate.png)

        应会看到在屏幕上打印的消息以及所调用操作的结果（在这里，我们将看到空元组， `()` 因为我们的操作只返回一个 `Unit` 类型）。

## <a name="next-steps"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
