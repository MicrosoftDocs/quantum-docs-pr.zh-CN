---
title: 带有量程机器学习库的基本分类
description: '了解如何使用 Microsoft QDK 的量程机器学习库来执行用 Q # 编写的量程顺序分类器。'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274421"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>基本分类：将数据与 QDK 进行分类

在本快速入门中，你将学习如何使用 QDK 的量程机器学习库来执行用 Q # 编写的量程顺序分类器。 

在本指南中，我们将使用 "Q #" 中定义的分类器结构来使用半形数据集。

## <a name="prerequisites"></a>先决条件

- Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。
- 为[Python 主机程序](xref:microsoft.quantum.install.python)或[c # 宿主程序](xref:microsoft.quantum.install.cs)创建 Q # 项目。

## <a name="host-program"></a>主机程序

主机程序由三个部分组成：

- 加载数据集并为模型选择一组起始参数。
- 执行训练以确定模型的参数和偏置。
- 验证模型以确定其准确性

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[在 Visual Studio Code 或命令行中使用 Python](#tab/tabid-python)

    若要运行你是 Python 中的 Q # 分类器，请将以下代码另存为 `host.py` 。 请记住，还需要在 `Training.qs` 本教程后面部分介绍的 Q # 文件。

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    然后便可以从命令行运行 Python 主机程序：

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[在 Visual Studio Code 或命令行中使用 C#](#tab/tabid-csharp)

    若要运行 c # 中的 Q # 分类器，请将以下代码另存为 `Host.cs` 。 请记住，还需要在 `Training.qs` 本教程后面部分介绍的 Q # 文件。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    然后便可以从命令行运行 C# 主机程序：

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[在 Visual Studio 2019 中使用 C#](#tab/tabid-vs2019)

    若要从 Visual Studio 中的 c # 运行新的 Q # 程序，请修改 `Host.cs` 以包含以下 c # 代码。 请记住，还需要在 `Training.qs` 本教程后面部分介绍的 Q # 文件。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    然后按 F5，此时系统就会开始执行程序并弹出一个新窗口，其中包含以下结果： 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q \# 分类器代码

现在让我们看看如何在 Q # 中定义主机程序调用的操作。
我们将以下代码保存到名为的文件中 `Training.qs` 。

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

在上面的代码中定义的最重要的函数和操作包括：

- `ClassifierStructure() : ControlledRotation[]`：在此函数中，我们通过添加所需的受控入口层来设置线路模型的结构。 此步骤类似于按顺序深入学习模型中的神经元层的声明。
- `TrainHalfMoonModel() : (Double[], Double)`：此操作是代码的核心部分并定义培训。 在这里，我们将从库中包含的数据集中加载示例，为训练设置了超级参数和初始参数，并通过调用库中包含的操作开始培训 `TrainSequentialClassifier` 。 它输出参数和确定分类器的偏差。
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`：此操作定义用于评估模型的验证过程。 在这里，我们将加载用于验证的示例、每个样本的度量值和容差。 它输出所选的一批样本的 misclassifications 数，用于验证。

## <a name="next-steps"></a>后续步骤

首先，您可以与代码一起玩，尝试更改一些参数，以查看它如何影响培训。 然后，在下一教程中[，您](xref:microsoft.quantum.libraries.machine-learning.design)将学习如何定义分类器的结构。
