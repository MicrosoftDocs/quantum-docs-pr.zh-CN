---
title: '用 Q # Jupyter 笔记本进行开发'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831063"
---
# <a name="develop-with-q-jupyter-notebooks"></a>用 Q # Jupyter 笔记本进行开发

在 Q # Jupyter 笔记本上安装用于开发 Q # 操作的 QDK。

Jupyter 笔记本允许就地执行的代码与说明、注释和其他内容。 此环境非常适合用于编写带有嵌入的解释或量子计算交互式教程的 Q # 代码。 下面是开始创建自己的 Q# 笔记本时需要执行的操作。

IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。

> [!NOTE]
> * 在 Q # Jupyter 笔记本中，只能运行 Q # 代码，不能从外部主机程序（例如 Python 或C#文件）调用操作。 如果你的目标是将外部传统主机程序与量程计划结合使用，则此环境不适合。

1. 必备组件

    - [Python](https://www.python.org/downloads/) 3.6 或更高版本
    - [Jupyter 笔记本](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)

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


    - 在新单元中，使用 `%simulate` 命令执行刚刚创建的操作（在模拟器中）：

        ![包含 %simulate magic 的 Jupyter 笔记本单元格](~/media/install-guide-jupyter-simulate.png)

        你应看到在屏幕上显示的消息以及所调用操作的结果（在这里，我们会看到空的元组 `()`，因为我们的操作只返回 `Unit` 类型）。

## <a name="whats-next"></a>还有什么？

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。