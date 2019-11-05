---
title: 在 Q# 中运行 Grover 搜索算法 - Quantum 开发工具
description: 生成一个 Q# 项目，以展示 Grover 搜索这种经典的量子算法。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443930"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="4e593-103">快速入门：在 Q# 中实现 Grover 搜索算法</span><span class="sxs-lookup"><span data-stu-id="4e593-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="4e593-104">本快速入门介绍如何构建并运行 Grover 搜索，以便加快非结构化数据的搜索速度。</span><span class="sxs-lookup"><span data-stu-id="4e593-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="4e593-105">Grover 搜索是最常用量子计算算法之一。这个相对较小的 Q# 实现可以让你感受一下使用高级 Q# 量子编程语言进行量子解决方案编程（用于表达量子算法）的部分优势。</span><span class="sxs-lookup"><span data-stu-id="4e593-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="4e593-106">在指南末尾，我们会看到模拟输出。该输出表明我们已经在未排序条目的列表中成功找到一个特定的字符串，所花时间远远少于在经典计算机上搜索整个列表所花的时间。</span><span class="sxs-lookup"><span data-stu-id="4e593-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="4e593-107">Grover 算法在非结构化数据列表中搜索特定项。</span><span class="sxs-lookup"><span data-stu-id="4e593-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="4e593-108">例如，它可以回答如下问题：从一副纸牌中抽出的这张纸牌是红桃 A 吗？</span><span class="sxs-lookup"><span data-stu-id="4e593-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="4e593-109">特定项的标签称为“标记输入”  。</span><span class="sxs-lookup"><span data-stu-id="4e593-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="4e593-110">使用 Grover 搜索算法，可以保证量子计算机运行此搜索的步数少于所搜索列表中的项目数，这是经典算法无法做到的。</span><span class="sxs-lookup"><span data-stu-id="4e593-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="4e593-111">当从一副纸牌中抽一张纸牌时，提高的速度可以忽略不计，但在包含数百万或数十亿个项的列表中，这种效果是显而易见的。</span><span class="sxs-lookup"><span data-stu-id="4e593-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="4e593-112">只需几行代码，就能生成 Grover 搜索算法。</span><span class="sxs-lookup"><span data-stu-id="4e593-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e593-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="4e593-113">Prerequisites</span></span>

- <span data-ttu-id="4e593-114">Microsoft [Quantum 开发工具包][install]。</span><span class="sxs-lookup"><span data-stu-id="4e593-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="4e593-115">Grover 搜索算法有什么作用？</span><span class="sxs-lookup"><span data-stu-id="4e593-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="4e593-116">Grover 算法会询问列表中的某一项是否是我门正在搜索的项。</span><span class="sxs-lookup"><span data-stu-id="4e593-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="4e593-117">其实现方法是，通过每个系数（即概率幅度，表示该特定索引恰好是你所搜索索引的可能性）来构造列表索引的量子叠加。</span><span class="sxs-lookup"><span data-stu-id="4e593-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="4e593-118">该算法的核心是两个步骤，逐渐增加所搜索索引的系数，直到该系数的概率幅度接近 1。</span><span class="sxs-lookup"><span data-stu-id="4e593-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="4e593-119">增加的增量值应少于列表中的项数。</span><span class="sxs-lookup"><span data-stu-id="4e593-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="4e593-120">这就是 Grover 搜索算法执行搜索的步骤少于任何经典算法的原因。</span><span class="sxs-lookup"><span data-stu-id="4e593-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Grover 搜索算法的功能示意图](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="4e593-122">编写代码</span><span class="sxs-lookup"><span data-stu-id="4e593-122">Write the code</span></span>

1. <span data-ttu-id="4e593-123">使用 Quantum 开发工具包在你选择的开发坏境中[创建一个新的 Q# 项目](xref:microsoft.quantum.howto.createproject)，并将其命名为 `Grover`。</span><span class="sxs-lookup"><span data-stu-id="4e593-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="4e593-124">在新项目中，将以下代码添加到 `Operations.qs` 文件中：</span><span class="sxs-lookup"><span data-stu-id="4e593-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="4e593-125">要定义搜索列表，请创建一个新文件 `Reflections.qs`，并粘贴以下代码：</span><span class="sxs-lookup"><span data-stu-id="4e593-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="4e593-126">`ReflectAboutMarked` 运算定义要搜索的标记输入：0 和 1 交替的字符串。</span><span class="sxs-lookup"><span data-stu-id="4e593-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="4e593-127">此示例对标记输入进行硬编码，并且可以扩展为搜索不同的输入或针对任何输入进行通用化。</span><span class="sxs-lookup"><span data-stu-id="4e593-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="4e593-128">接下来，运行你的新 Q# 程序，以查找 `ReflectAboutMarked` 标记的项。</span><span class="sxs-lookup"><span data-stu-id="4e593-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="4e593-129">在 Visual Studio Code 或命令行中使用 Python</span><span class="sxs-lookup"><span data-stu-id="4e593-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="4e593-130">要从 Python 运行你的新 Q# 程序，请将以下代码另存为 `host.py`：</span><span class="sxs-lookup"><span data-stu-id="4e593-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="4e593-131">然后便可以从命令行运行 Python 主机程序：</span><span class="sxs-lookup"><span data-stu-id="4e593-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="4e593-132">在 Visual Studio Code 或命令行中使用 C#</span><span class="sxs-lookup"><span data-stu-id="4e593-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="4e593-133">要从 C# 运行你的新 Q# 程序，请修改 `Driver.cs` 以包含以下 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="4e593-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="4e593-134">然后便可以从命令行运行 C# 主机程序：</span><span class="sxs-lookup"><span data-stu-id="4e593-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="4e593-135">在 Visual Studio 2019 中使用 C#</span><span class="sxs-lookup"><span data-stu-id="4e593-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="4e593-136">在 Visual Studio 中，若要通过 C# 运行新的 Q# 程序，请修改 `Driver.cs`，使之包含以下 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="4e593-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="4e593-137">然后按 F5，此时系统就会开始执行程序并弹出一个新窗口，其中包含以下结果：</span><span class="sxs-lookup"><span data-stu-id="4e593-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

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

    <span data-ttu-id="4e593-138">`ReflectAboutMarked` 运算仅调用四次，但是 Q# 程序能够在 $2^{5} = 32$ 个可能的输入中找到“01010”输入！</span><span class="sxs-lookup"><span data-stu-id="4e593-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e593-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4e593-139">Next steps</span></span>

<span data-ttu-id="4e593-140">如果喜欢本快速入门指南，请查看以下部分资源，详细了解有关使用 Q# 编写自己的量子应用程序：</span><span class="sxs-lookup"><span data-stu-id="4e593-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="4e593-141">回到 QDK 入门指南</span><span class="sxs-lookup"><span data-stu-id="4e593-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="4e593-142">尝试使用更多常用 Grover 搜索算法[示例](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span><span class="sxs-lookup"><span data-stu-id="4e593-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="4e593-143">详细了解 Quantum Katas 的 Grover 搜索</span><span class="sxs-lookup"><span data-stu-id="4e593-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="4e593-144">详细了解[振幅放大](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification)：支持 Grover 搜索算法的量子计算技术</span><span class="sxs-lookup"><span data-stu-id="4e593-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="4e593-145">量子计算概念</span><span class="sxs-lookup"><span data-stu-id="4e593-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="4e593-146">Quantum 开发工具包示例</span><span class="sxs-lookup"><span data-stu-id="4e593-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
