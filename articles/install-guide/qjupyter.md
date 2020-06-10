---
title: 使用 Q# Jupyter Notebooks 进行开发
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630327"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="77dab-102">使用 Q# Jupyter Notebooks 进行开发</span><span class="sxs-lookup"><span data-stu-id="77dab-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="77dab-103">在 Q # Jupyter 笔记本上安装用于开发 Q # 操作的 QDK。</span><span class="sxs-lookup"><span data-stu-id="77dab-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="77dab-104">Jupyter 笔记本允许就地执行的代码与说明、注释和其他内容。</span><span class="sxs-lookup"><span data-stu-id="77dab-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="77dab-105">此环境非常适合用于编写带有嵌入的解释或量子计算交互式教程的 Q # 代码。</span><span class="sxs-lookup"><span data-stu-id="77dab-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="77dab-106">下面是开始创建自己的 Q# 笔记本时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="77dab-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="77dab-107">IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="77dab-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="77dab-108">在 Q # Jupyter 笔记本中，只能运行 Q # 代码，不能从外部主机程序（例如 Python 或 c # 文件）中调用操作。</span><span class="sxs-lookup"><span data-stu-id="77dab-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="77dab-109">如果你的目标是将外部传统主机程序与量程计划结合使用，则此环境不适合。</span><span class="sxs-lookup"><span data-stu-id="77dab-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="77dab-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="77dab-110">Prerequisites</span></span>

    - <span data-ttu-id="77dab-111">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="77dab-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="77dab-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="77dab-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="77dab-113">.NET Core SDK 3。1</span><span class="sxs-lookup"><span data-stu-id="77dab-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="77dab-114">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="77dab-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="77dab-115">如果在此步骤中遇到错误 `dotnet iqsharp install` ，请打开新的终端窗口，然后重试。</span><span class="sxs-lookup"><span data-stu-id="77dab-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="77dab-116">如果这仍不起作用，请尝试查找安装的 `dotnet-iqsharp` 工具（在 Windows 上 `dotnet-iqsharp.exe` ）并运行：</span><span class="sxs-lookup"><span data-stu-id="77dab-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="77dab-117">其中 `/path/to/dotnet-iqsharp` 应替换为 `dotnet-iqsharp` 文件系统中的工具的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="77dab-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="77dab-118">通常，这会在 `.dotnet/tools` 用户配置文件文件夹下。</span><span class="sxs-lookup"><span data-stu-id="77dab-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="77dab-119">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="77dab-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="77dab-120">运行以下命令以启动 Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="77dab-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="77dab-121">若要打开 Jupyter Notebook，请将命令行提供的 URL 复制并粘贴到浏览器中。</span><span class="sxs-lookup"><span data-stu-id="77dab-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="77dab-122">使用 Q # 内核创建 Jupyter Notebook，并将以下代码添加到第一个笔记本单元：</span><span class="sxs-lookup"><span data-stu-id="77dab-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="77dab-123">运行以下 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="77dab-123">Run this cell of the notebook:</span></span>

        ![带有 Q # 代码的单元格 Jupyter Notebook](~/media/install-guide-jupyter.png)

        <span data-ttu-id="77dab-125">应在单元格的输出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="77dab-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="77dab-126">在 Jupyter Notebook 中运行时，将编译 Q # 代码，然后笔记本将输出找到的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="77dab-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="77dab-127">在新单元中，使用命令执行你刚刚在模拟器中创建的操作 `%simulate` ：</span><span class="sxs-lookup"><span data-stu-id="77dab-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![具有% 模拟幻数的 Jupyter Notebook 单元](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="77dab-129">应会看到在屏幕上打印的消息以及所调用操作的结果（在这里，我们将看到空元组， `()` 因为我们的操作只返回一个 `Unit` 类型）。</span><span class="sxs-lookup"><span data-stu-id="77dab-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="77dab-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="77dab-130">Next steps</span></span>

<span data-ttu-id="77dab-131">现在，你已安装了用于 Q # Jupyter 笔记本的 QDK，接下来可以通过在 Jupyter Notebook 环境中直接编写 Q # 代码来编写并运行[第一个量程程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="77dab-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="77dab-132">有关使用 Q # Jupyter 笔记本可以执行的操作的更多示例，请参阅：</span><span class="sxs-lookup"><span data-stu-id="77dab-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="77dab-133">[问题解答到 Q # 和 Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="77dab-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="77dab-134">在这里，你会看到一个 Q # Jupyter Notebook，其中演示了如何在此环境中使用 Q #。</span><span class="sxs-lookup"><span data-stu-id="77dab-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="77dab-135">[量子 Katas](xref:microsoft.quantum.overview.katas)，一系列自控进度的教程和编程练习集，采用 Q # Jupyter 笔记本的形式。</span><span class="sxs-lookup"><span data-stu-id="77dab-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="77dab-136">[量程 Katas 教程](https://github.com/microsoft/QuantumKatas#tutorial-topics)是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="77dab-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="77dab-137">量程 Katas 旨在同时为你讲授量程计算和 Q # 编程的元素。</span><span class="sxs-lookup"><span data-stu-id="77dab-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="77dab-138">这是可以使用 Q # Jupyter 笔记本创建的内容的一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="77dab-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
