---
title: 使用 Q# 运行 Grover 搜索算法 - Quantum 开发工具
description: 生成一个 Q# 项目，以展示 Grover 搜索这种经典的量子算法。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c67ccd16957ceef694552bdd9c073ba5a35d8aaf
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686830"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="d3a91-103">快速入门：使用 Q\# 实现 Grover 搜索算法</span><span class="sxs-lookup"><span data-stu-id="d3a91-103">Quickstart: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="d3a91-104">本快速入门介绍如何构建并运行 Grover 搜索，以便加快非结构化数据的搜索速度。</span><span class="sxs-lookup"><span data-stu-id="d3a91-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="d3a91-105">Grover 搜索是最常用量子计算算法之一。这个相对较小的 Q# 实现可以让你感受一下使用高级 Q# 量子编程语言进行量子解决方案编程（用于表达量子算法）的部分优势。</span><span class="sxs-lookup"><span data-stu-id="d3a91-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="d3a91-106">在指南末尾，我们会看到模拟输出。该输出表明我们已经在未排序条目的列表中成功找到一个特定的字符串，所花时间远远少于在经典计算机上搜索整个列表所花的时间。</span><span class="sxs-lookup"><span data-stu-id="d3a91-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="d3a91-107">Grover 算法在非结构化数据列表中搜索特定项。</span><span class="sxs-lookup"><span data-stu-id="d3a91-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="d3a91-108">例如，它可以回答如下问题：从一副纸牌中抽出的这张纸牌是红桃 A 吗？</span><span class="sxs-lookup"><span data-stu-id="d3a91-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="d3a91-109">特定项的标签称为“标记输入”  。</span><span class="sxs-lookup"><span data-stu-id="d3a91-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="d3a91-110">使用 Grover 搜索算法，可以保证量子计算机运行此搜索的步数少于所搜索列表中的项目数，这是经典算法无法做到的。</span><span class="sxs-lookup"><span data-stu-id="d3a91-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="d3a91-111">当从一副纸牌中抽一张纸牌时，提高的速度可以忽略不计，但在包含数百万或数十亿个项的列表中，这种效果是显而易见的。</span><span class="sxs-lookup"><span data-stu-id="d3a91-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="d3a91-112">只需几行代码，就能生成 Grover 搜索算法。</span><span class="sxs-lookup"><span data-stu-id="d3a91-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3a91-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="d3a91-113">Prerequisites</span></span>

- <span data-ttu-id="d3a91-114">Microsoft [Quantum 开发工具包][install]。</span><span class="sxs-lookup"><span data-stu-id="d3a91-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="d3a91-115">Grover 搜索算法有什么作用？</span><span class="sxs-lookup"><span data-stu-id="d3a91-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="d3a91-116">Grover 算法会询问列表中的某一项是否是我门正在搜索的项。</span><span class="sxs-lookup"><span data-stu-id="d3a91-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="d3a91-117">其实现方法是，通过每个系数（即概率幅度，表示该特定索引恰好是你所搜索索引的可能性）来构造列表索引的量子叠加。</span><span class="sxs-lookup"><span data-stu-id="d3a91-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="d3a91-118">该算法的核心是两个步骤，逐渐增加所搜索索引的系数，直到该系数的概率幅度接近 1。</span><span class="sxs-lookup"><span data-stu-id="d3a91-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="d3a91-119">增加的增量值应少于列表中的项数。</span><span class="sxs-lookup"><span data-stu-id="d3a91-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="d3a91-120">这就是 Grover 搜索算法执行搜索的步骤少于任何经典算法的原因。</span><span class="sxs-lookup"><span data-stu-id="d3a91-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Grover 搜索算法的功能示意图](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="d3a91-122">编写代码</span><span class="sxs-lookup"><span data-stu-id="d3a91-122">Write the code</span></span>

1. <span data-ttu-id="d3a91-123">使用 Quantum 开发工具包在你选择的开发坏境中[创建一个新的 Q# 项目](xref:microsoft.quantum.howto.createproject)，并将其命名为 `Grover`。</span><span class="sxs-lookup"><span data-stu-id="d3a91-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="d3a91-124">在新项目中，将以下代码添加到 `Program.qs` 文件中：</span><span class="sxs-lookup"><span data-stu-id="d3a91-124">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="d3a91-125">要定义搜索列表，请创建一个新文件 `Reflections.qs`，并粘贴以下代码：</span><span class="sxs-lookup"><span data-stu-id="d3a91-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="d3a91-126">`ReflectAboutMarked` 运算定义要搜索的标记输入：0 和 1 交替的字符串。</span><span class="sxs-lookup"><span data-stu-id="d3a91-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="d3a91-127">此示例对标记输入进行硬编码，并且可以扩展为搜索不同的输入或针对任何输入进行通用化。</span><span class="sxs-lookup"><span data-stu-id="d3a91-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="d3a91-128">接下来，运行你的新 Q# 程序，以查找 `ReflectAboutMarked` 标记的项。</span><span class="sxs-lookup"><span data-stu-id="d3a91-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="d3a91-129">Q# 命令行应用程序与 Visual Studio 或 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d3a91-129">Q# command line applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="d3a91-130">可执行文件将在仿真器或资源估计器上运行使用 `@EntryPoint()` 特性标记的操作或函数，具体取决于项目配置和命令行选项。</span><span class="sxs-lookup"><span data-stu-id="d3a91-130">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="d3a91-131">在 Visual Studio 中，只需按 Ctrl + F5 即可执行该脚本。</span><span class="sxs-lookup"><span data-stu-id="d3a91-131">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="d3a91-132">在 VS Code 中，通过在终端中键入以下内容来首次生成 `Program.qs`：</span><span class="sxs-lookup"><span data-stu-id="d3a91-132">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="d3a91-133">对于后续运行，则无需重新生成它。</span><span class="sxs-lookup"><span data-stu-id="d3a91-133">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="d3a91-134">若要运行它，请键入以下命令并按 Enter：</span><span class="sxs-lookup"><span data-stu-id="d3a91-134">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="d3a91-135">应当会看到终端中显示了以下消息：</span><span class="sxs-lookup"><span data-stu-id="d3a91-135">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="d3a91-136">这是因为你未指定想要使用的量子位的数目，因此终端显示了可用于该可执行文件的命令。</span><span class="sxs-lookup"><span data-stu-id="d3a91-136">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="d3a91-137">如果想要使用 5 个量子位，应键入：</span><span class="sxs-lookup"><span data-stu-id="d3a91-137">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="d3a91-138">按 Enter 后应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="d3a91-138">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="d3a91-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d3a91-139">Next steps</span></span>

<span data-ttu-id="d3a91-140">如果喜欢本快速入门指南，请查看以下部分资源，详细了解有关使用 Q# 编写自己的量子应用程序：</span><span class="sxs-lookup"><span data-stu-id="d3a91-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="d3a91-141">回到 QDK 入门指南</span><span class="sxs-lookup"><span data-stu-id="d3a91-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="d3a91-142">尝试使用更多常用 Grover 搜索算法[示例](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span><span class="sxs-lookup"><span data-stu-id="d3a91-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="d3a91-143">详细了解 Quantum Katas 的 Grover 搜索</span><span class="sxs-lookup"><span data-stu-id="d3a91-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="d3a91-144">详细了解[振幅放大][amplitude-amplification]：支持 Grover 搜索算法的量子计算技术</span><span class="sxs-lookup"><span data-stu-id="d3a91-144">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="d3a91-145">量子计算概念</span><span class="sxs-lookup"><span data-stu-id="d3a91-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="d3a91-146">Quantum 开发工具包示例</span><span class="sxs-lookup"><span data-stu-id="d3a91-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
