---
title: 带有量程机器学习库的基本分类
description: 了解如何运行 Q# 使用 MICROSOFT QDK 的量程机器学习库中编写的量程顺序分类器。
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5dc4614b9992e2c6b9f8ff4b839c0929ec8cab7c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833723"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="6b97a-103">基本分类：将数据与 QDK 进行分类</span><span class="sxs-lookup"><span data-stu-id="6b97a-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="6b97a-104">在本快速入门教程中，你将学习如何 Q# 使用 QDK 的量程机器学习库来运行在中编写的量程顺序分类器。</span><span class="sxs-lookup"><span data-stu-id="6b97a-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="6b97a-105">在本指南中，我们将使用中定义的分类器结构来使用半形数据集 Q# 。</span><span class="sxs-lookup"><span data-stu-id="6b97a-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b97a-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="6b97a-106">Prerequisites</span></span>

- <span data-ttu-id="6b97a-107">Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="6b97a-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="6b97a-108">Q#为[Python 主机程序](xref:microsoft.quantum.install.python)或[c # 宿主程序](xref:microsoft.quantum.install.cs)创建项目。</span><span class="sxs-lookup"><span data-stu-id="6b97a-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="6b97a-109">主机程序</span><span class="sxs-lookup"><span data-stu-id="6b97a-109">Host program</span></span>

<span data-ttu-id="6b97a-110">主机程序由三个部分组成：</span><span class="sxs-lookup"><span data-stu-id="6b97a-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="6b97a-111">加载数据集并为模型选择一组起始参数。</span><span class="sxs-lookup"><span data-stu-id="6b97a-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="6b97a-112">运行训练以确定模型的参数和偏置。</span><span class="sxs-lookup"><span data-stu-id="6b97a-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="6b97a-113">验证模型以确定其准确性</span><span class="sxs-lookup"><span data-stu-id="6b97a-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="6b97a-114">在 Visual Studio Code 或命令行中使用 Python</span><span class="sxs-lookup"><span data-stu-id="6b97a-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="6b97a-115">若要运行你是 Q# Python 中的分类器，请将以下代码另存为 `host.py` 。</span><span class="sxs-lookup"><span data-stu-id="6b97a-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="6b97a-116">请记住，还需要 Q# `Training.qs` 在本教程后面部分介绍的文件。</span><span class="sxs-lookup"><span data-stu-id="6b97a-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="6b97a-117">然后便可以从命令行运行 Python 主机程序：</span><span class="sxs-lookup"><span data-stu-id="6b97a-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="6b97a-118">在 Visual Studio Code 或命令行中使用 C#</span><span class="sxs-lookup"><span data-stu-id="6b97a-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="6b97a-119">若要运行的是 Q# c # 中的分类器，请将以下代码另存为 `Host.cs` 。</span><span class="sxs-lookup"><span data-stu-id="6b97a-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="6b97a-120">请记住，还需要 Q# `Training.qs` 在本教程后面部分介绍的文件。</span><span class="sxs-lookup"><span data-stu-id="6b97a-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="6b97a-121">然后便可以从命令行运行 C# 主机程序：</span><span class="sxs-lookup"><span data-stu-id="6b97a-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="6b97a-122">在 Visual Studio 2019 中使用 C#</span><span class="sxs-lookup"><span data-stu-id="6b97a-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="6b97a-123">若要 Q# 从 Visual Studio 中的 c # 运行新程序，请修改 `Host.cs` 以包含以下 c # 代码。</span><span class="sxs-lookup"><span data-stu-id="6b97a-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="6b97a-124">请记住，还需要 Q# `Training.qs` 在本教程后面部分介绍的文件。</span><span class="sxs-lookup"><span data-stu-id="6b97a-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="6b97a-125">按 F5，程序将开始运行。</span><span class="sxs-lookup"><span data-stu-id="6b97a-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="6b97a-126">新窗口将显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="6b97a-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="6b97a-127">Q \# 分类器代码</span><span class="sxs-lookup"><span data-stu-id="6b97a-127">Q\# classifier code</span></span>

<span data-ttu-id="6b97a-128">现在让我们看一下如何在中定义主机程序调用的操作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="6b97a-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="6b97a-129">我们将以下代码保存到名为的文件中 `Training.qs` 。</span><span class="sxs-lookup"><span data-stu-id="6b97a-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="6b97a-130">在上面的代码中定义的最重要的函数和操作包括：</span><span class="sxs-lookup"><span data-stu-id="6b97a-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="6b97a-131">`ClassifierStructure() : ControlledRotation[]` ：在此函数中，我们通过添加所需的受控入口层来设置线路模型的结构。</span><span class="sxs-lookup"><span data-stu-id="6b97a-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="6b97a-132">此步骤类似于按顺序深入学习模型中的神经元层的声明。</span><span class="sxs-lookup"><span data-stu-id="6b97a-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="6b97a-133">`TrainHalfMoonModel() : (Double[], Double)` ：此操作是代码的核心部分并定义培训。</span><span class="sxs-lookup"><span data-stu-id="6b97a-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="6b97a-134">在这里，我们将从库中包含的数据集中加载示例，为训练设置了超级参数和初始参数，并通过调用库中包含的操作开始培训 `TrainSequentialClassifier` 。</span><span class="sxs-lookup"><span data-stu-id="6b97a-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="6b97a-135">它输出参数和确定分类器的偏差。</span><span class="sxs-lookup"><span data-stu-id="6b97a-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="6b97a-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` ：此操作定义用于评估模型的验证过程。</span><span class="sxs-lookup"><span data-stu-id="6b97a-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="6b97a-137">在这里，我们将加载用于验证的示例、每个样本的度量值和容差。</span><span class="sxs-lookup"><span data-stu-id="6b97a-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="6b97a-138">它输出所选的一批样本的 misclassifications 数，用于验证。</span><span class="sxs-lookup"><span data-stu-id="6b97a-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b97a-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b97a-139">Next steps</span></span>

<span data-ttu-id="6b97a-140">首先，您可以与代码一起玩，尝试更改一些参数，以查看它如何影响培训。</span><span class="sxs-lookup"><span data-stu-id="6b97a-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="6b97a-141">然后，在下一教程中 [，您](xref:microsoft.quantum.libraries.machine-learning.design)将学习如何定义分类器的结构。</span><span class="sxs-lookup"><span data-stu-id="6b97a-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
