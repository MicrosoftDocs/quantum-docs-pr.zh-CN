---
title: 在 Q# 中运行 Grover 搜索算法 - Quantum 开发工具
description: 生成一个 Q# 项目，以展示 Grover 搜索这种经典的量子算法。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906944"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>快速入门：在 Q# 中实现 Grover 搜索算法

本快速入门介绍如何构建并运行 Grover 搜索，以便加快非结构化数据的搜索速度。  Grover 搜索是最常用量子计算算法之一。这个相对较小的 Q# 实现可以让你感受一下使用高级 Q# 量子编程语言进行量子解决方案编程（用于表达量子算法）的部分优势。  在指南末尾，我们会看到模拟输出。该输出表明我们已经在未排序条目的列表中成功找到一个特定的字符串，所花时间远远少于在经典计算机上搜索整个列表所花的时间。

Grover 算法在非结构化数据列表中搜索特定项。 例如，它可以回答如下问题：从一副纸牌中抽出的这张纸牌是红桃 A 吗？ 特定项的标签称为“标记输入”  。

使用 Grover 搜索算法，可以保证量子计算机运行此搜索的步数少于所搜索列表中的项目数，这是经典算法无法做到的。 当从一副纸牌中抽一张纸牌时，提高的速度可以忽略不计，但在包含数百万或数十亿个项的列表中，这种效果是显而易见的。

只需几行代码，就能生成 Grover 搜索算法。

## <a name="prerequisites"></a>先决条件

- Microsoft [Quantum 开发工具包][install]。

## <a name="what-does-grovers-search-algorithm-do"></a>Grover 搜索算法有什么作用？

Grover 算法会询问列表中的某一项是否是我门正在搜索的项。 其实现方法是，通过每个系数（即概率幅度，表示该特定索引恰好是你所搜索索引的可能性）来构造列表索引的量子叠加。

该算法的核心是两个步骤，逐渐增加所搜索索引的系数，直到该系数的概率幅度接近 1。

增加的增量值应少于列表中的项数。 这就是 Grover 搜索算法执行搜索的步骤少于任何经典算法的原因。

![Grover 搜索算法的功能示意图](~/media/grover.png)

## <a name="write-the-code"></a>编写代码

1. 使用 Quantum 开发工具包在你选择的开发坏境中[创建一个新的 Q# 项目](xref:microsoft.quantum.howto.createproject)，并将其命名为 `Grover`。

1. 在新项目中，将以下代码添加到 `Operations.qs` 文件中：

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. 要定义搜索列表，请创建一个新文件 `Reflections.qs`，并粘贴以下代码：

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    `ReflectAboutMarked` 运算定义要搜索的标记输入：0 和 1 交替的字符串。 此示例对标记输入进行硬编码，并且可以扩展为搜索不同的输入或针对任何输入进行通用化。

1. 接下来，运行你的新 Q# 程序，以查找 `ReflectAboutMarked` 标记的项。

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[在 Visual Studio Code 或命令行中使用 Python](#tab/tabid-python)

    要从 Python 运行你的新 Q# 程序，请将以下代码另存为 `host.py`：

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    然后便可以从命令行运行 Python 主机程序：

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[在 Visual Studio Code 或命令行中使用 C#](#tab/tabid-csharp)

    要从 C# 运行你的新 Q# 程序，请修改 `Driver.cs` 以包含以下 C# 代码：

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    然后便可以从命令行运行 C# 主机程序：

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[在 Visual Studio 2019 中使用 C#](#tab/tabid-vs2019)

    在 Visual Studio 中，若要通过 C# 运行新的 Q# 程序，请修改 `Driver.cs`，使之包含以下 C# 代码：

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    然后按 F5，此时系统就会开始执行程序并弹出一个新窗口，其中包含以下结果： 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    `ReflectAboutMarked` 运算仅调用四次，但是 Q# 程序能够在 $2^{5} = 32$ 个可能的输入中找到“01010”输入！

## <a name="next-steps"></a>后续步骤

如果喜欢本快速入门指南，请查看以下部分资源，详细了解有关使用 Q# 编写自己的量子应用程序：

- [回到 QDK 入门指南](xref:microsoft.quantum.welcome)
- 尝试使用更多常用 Grover 搜索算法[示例](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)
- [详细了解 Quantum Katas 的 Grover 搜索](xref:microsoft.quantum.overview.katas)
- 详细了解[振幅放大](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification)：支持 Grover 搜索算法的量子计算技术
- [量子计算概念](xref:microsoft.quantum.concepts.intro)
- [Quantum 开发工具包示例](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
