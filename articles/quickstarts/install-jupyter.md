---
title: 使用 Q# Jupyter Notebook 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274032"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="22879-102">使用 Q# Jupyter Notebook 进行开发</span><span class="sxs-lookup"><span data-stu-id="22879-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="22879-103">在 Q# Jupyter 笔记本上安装用于开发 Q# 操作的 QDK。</span><span class="sxs-lookup"><span data-stu-id="22879-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="22879-104">Jupyter Notebook 支持在包含说明、注释和其他内容的情况下就地执行代码。</span><span class="sxs-lookup"><span data-stu-id="22879-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="22879-105">此环境非常适合编写包含嵌入式说明的 Q# 代码或量子计算交互式教程。</span><span class="sxs-lookup"><span data-stu-id="22879-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="22879-106">下面是开始创建自己的 Q# 笔记本时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="22879-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="22879-107">IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="22879-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="22879-108">在 Q# Jupyter 笔记本中，只能运行 Q# 代码，不能从外部主机程序（例如 Python 或 C# 文件）调用操作。</span><span class="sxs-lookup"><span data-stu-id="22879-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="22879-109">如果你的目标是将外部传统主机程序与量子程序结合，则此环境不适合。</span><span class="sxs-lookup"><span data-stu-id="22879-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="22879-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="22879-110">Prerequisites</span></span>

    - <span data-ttu-id="22879-111">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="22879-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="22879-112">Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="22879-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="22879-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="22879-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="22879-114">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="22879-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="22879-115">如果在 `dotnet iqsharp install` 步骤中遇到错误，请打开新的终端窗口，然后重试。</span><span class="sxs-lookup"><span data-stu-id="22879-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="22879-116">如果仍有问题，请尝试查找安装的 `dotnet-iqsharp` 工具（在 Windows 上为 `dotnet-iqsharp.exe`）并运行：</span><span class="sxs-lookup"><span data-stu-id="22879-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="22879-117">其中 `/path/to/dotnet-iqsharp` 应替换为文件系统中 `dotnet-iqsharp` 工具的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="22879-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="22879-118">通常，该工具在用户配置文件文件夹中的 `.dotnet/tools` 下。</span><span class="sxs-lookup"><span data-stu-id="22879-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="22879-119">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="22879-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="22879-120">运行以下命令以启动 Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="22879-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="22879-121">若要打开 Jupyter Notebook，请复制命令行提供的 URL 并将其粘贴到浏览器中。</span><span class="sxs-lookup"><span data-stu-id="22879-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="22879-122">使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="22879-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="22879-123">运行以下 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="22879-123">Run this cell of the notebook:</span></span>

        ![包含 Q# 代码的 Jupyter Notebook 单元格](~/media/install-guide-jupyter.png)

        <span data-ttu-id="22879-125">应在单元格的输出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="22879-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="22879-126">在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且 Notebook 将输出找到的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="22879-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="22879-127">在新单元格中，使用 `%simulate` 命令执行刚刚创建的操作（在模拟器中）：</span><span class="sxs-lookup"><span data-stu-id="22879-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![包含 %simulate magic 的 Jupyter Notebook 单元格](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="22879-129">你应会看到屏幕上显示的消息以及所调用操作的结果（在本例中，我们会看到空的元组 `()`，因为操作只返回 `Unit` 类型）。</span><span class="sxs-lookup"><span data-stu-id="22879-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="22879-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22879-130">Next steps</span></span>

<span data-ttu-id="22879-131">现在，你已安装适用于 Q# Jupyter Notebook 的 QDK，接下来可以在 Jupyter Notebook 环境中直接编写 Q# 代码，从而完成并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="22879-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="22879-132">要了解更多关于使用 Q# Jupyter Notebook 可以执行的操作的示例，请参阅：</span><span class="sxs-lookup"><span data-stu-id="22879-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="22879-133">[Q# 和 Jupyter Notebook 简介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="22879-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="22879-134">这篇文章中介绍了 Q# Jupyter Notebook，演示了如何在此环境中使用 Q#。</span><span class="sxs-lookup"><span data-stu-id="22879-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="22879-135">[Quantum Katas](xref:microsoft.quantum.overview.katas) 是一系列采用 Q# Jupyter Notebook 形式的可自定进度的开放元代码教程和编程练习。</span><span class="sxs-lookup"><span data-stu-id="22879-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="22879-136">可以先从 [Quantum Katas 教程笔记本](https://github.com/microsoft/QuantumKatas#tutorial-topics)开始。</span><span class="sxs-lookup"><span data-stu-id="22879-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="22879-137">Quantum Katas 的目标是同时教授量子计算和 Q# 编程的要素。</span><span class="sxs-lookup"><span data-stu-id="22879-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="22879-138">它们很好地演示了可以使用 Q# Jupyter Notebook 创建哪种内容。</span><span class="sxs-lookup"><span data-stu-id="22879-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>