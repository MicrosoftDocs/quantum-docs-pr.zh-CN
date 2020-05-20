---
title: 使用 Q# Jupyter Notebooks 进行开发
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660771"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="7ead1-102">使用 Q# Jupyter Notebooks 进行开发</span><span class="sxs-lookup"><span data-stu-id="7ead1-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="7ead1-103">在 Q # Jupyter 笔记本上安装用于开发 Q # 操作的 QDK。</span><span class="sxs-lookup"><span data-stu-id="7ead1-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="7ead1-104">Jupyter 笔记本允许就地执行的代码与说明、注释和其他内容。</span><span class="sxs-lookup"><span data-stu-id="7ead1-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="7ead1-105">此环境非常适合用于编写带有嵌入的解释或量子计算交互式教程的 Q # 代码。</span><span class="sxs-lookup"><span data-stu-id="7ead1-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="7ead1-106">下面是开始创建自己的 Q# 笔记本时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7ead1-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="7ead1-107">IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="7ead1-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="7ead1-108">在 Q # Jupyter 笔记本中，只能运行 Q # 代码，不能从外部主机程序（例如 Python 或 c # 文件）中调用操作。</span><span class="sxs-lookup"><span data-stu-id="7ead1-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="7ead1-109">如果你的目标是将外部传统主机程序与量程计划结合使用，则此环境不适合。</span><span class="sxs-lookup"><span data-stu-id="7ead1-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="7ead1-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="7ead1-110">Pre-requisites</span></span>

    - <span data-ttu-id="7ead1-111">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7ead1-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="7ead1-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="7ead1-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="7ead1-113">.NET Core SDK 3。1</span><span class="sxs-lookup"><span data-stu-id="7ead1-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="7ead1-114">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="7ead1-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7ead1-115">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="7ead1-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7ead1-116">运行以下命令以启动 Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="7ead1-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="7ead1-117">若要打开 Jupyter Notebook，请将命令行提供的 URL 复制并粘贴到浏览器中。</span><span class="sxs-lookup"><span data-stu-id="7ead1-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="7ead1-118">使用 Q # 内核创建 Jupyter Notebook，并将以下代码添加到第一个笔记本单元：</span><span class="sxs-lookup"><span data-stu-id="7ead1-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="7ead1-119">运行以下 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="7ead1-119">Run this cell of the notebook:</span></span>

        ![带有 Q # 代码的单元格 Jupyter Notebook](~/media/install-guide-jupyter.png)

        <span data-ttu-id="7ead1-121">应在单元格的输出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="7ead1-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="7ead1-122">在 Jupyter Notebook 中运行时，将编译 Q # 代码，然后笔记本将输出找到的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="7ead1-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="7ead1-123">在新单元中，使用命令执行你刚刚在模拟器中创建的操作 `%simulate` ：</span><span class="sxs-lookup"><span data-stu-id="7ead1-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![具有% 模拟幻数的 Jupyter Notebook 单元](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="7ead1-125">应会看到在屏幕上打印的消息以及所调用操作的结果（在这里，我们将看到空元组， `()` 因为我们的操作只返回一个 `Unit` 类型）。</span><span class="sxs-lookup"><span data-stu-id="7ead1-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ead1-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7ead1-126">Next steps</span></span>

<span data-ttu-id="7ead1-127">现在，你已安装了用于 Q # Jupyter 笔记本的 QDK，接下来可以通过在 Jupyter Notebook 环境中直接编写 Q # 代码来编写并运行[第一个量程程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="7ead1-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="7ead1-128">有关使用 Q # Jupyter 笔记本可以执行的操作的更多示例，请参阅：</span><span class="sxs-lookup"><span data-stu-id="7ead1-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="7ead1-129">[问题解答到 Q # 和 Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="7ead1-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="7ead1-130">在这里，你会看到一个 Q # Jupyter Notebook，其中演示了如何在此环境中使用 Q #。</span><span class="sxs-lookup"><span data-stu-id="7ead1-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="7ead1-131">[量子 Katas](xref:microsoft.quantum.overview.katas)，一系列自控进度的教程和编程练习集，采用 Q # Jupyter 笔记本的形式。</span><span class="sxs-lookup"><span data-stu-id="7ead1-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="7ead1-132">[量程 Katas 教程](https://github.com/microsoft/QuantumKatas#tutorial-topics)是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="7ead1-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="7ead1-133">量程 Katas 旨在同时为你讲授量程计算和 Q # 编程的元素。</span><span class="sxs-lookup"><span data-stu-id="7ead1-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="7ead1-134">这是可以使用 Q # Jupyter 笔记本创建的内容的一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="7ead1-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
