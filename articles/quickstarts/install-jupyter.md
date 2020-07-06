---
title: 使用 Q# Jupyter Notebook 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 8a878e8f930f4b898f4de35751e4a39cc8716cec
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884222"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="3aed6-102">使用 Q# Jupyter Notebook 进行开发</span><span class="sxs-lookup"><span data-stu-id="3aed6-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="3aed6-103">在 Q# Jupyter 笔记本上安装用于开发 Q# 操作的 QDK。</span><span class="sxs-lookup"><span data-stu-id="3aed6-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="3aed6-104">Jupyter Notebook 支持在包含说明、注释和其他内容的情况下就地执行代码。</span><span class="sxs-lookup"><span data-stu-id="3aed6-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="3aed6-105">此环境非常适合编写包含嵌入式说明的 Q# 代码或量子计算交互式教程。</span><span class="sxs-lookup"><span data-stu-id="3aed6-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="3aed6-106">下面是开始创建自己的 Q# 笔记本时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3aed6-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

> [!NOTE]
> * <span data-ttu-id="3aed6-107">在 Q# Jupyter Notebooks 中，只能运行 Q# 代码，不能从外部主机程序（例如 Python 或 C# 文件）调用操作。</span><span class="sxs-lookup"><span data-stu-id="3aed6-107">In Q# Jupyter Notebooks, you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="3aed6-108">如果你的目标是将外部传统主机程序与量子程序结合，则此环境不适合。</span><span class="sxs-lookup"><span data-stu-id="3aed6-108">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

## <a name="install-the-iq-jupyter-kernel"></a><span data-ttu-id="3aed6-109">安装 IQ# Jupyter 内核</span><span class="sxs-lookup"><span data-stu-id="3aed6-109">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="3aed6-110">IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="3aed6-110">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="3aed6-111">使用 conda 进行安装（推荐）</span><span class="sxs-lookup"><span data-stu-id="3aed6-111">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="3aed6-112">安装 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。</span><span class="sxs-lookup"><span data-stu-id="3aed6-112">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span>

1. <span data-ttu-id="3aed6-113">打开 Anaconda 提示。</span><span class="sxs-lookup"><span data-stu-id="3aed6-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="3aed6-114">如果更想要使用 PowerShell 或 pwsh：请打开 shell，运行 `conda init powershell`，然后关闭再重新打开 shell。</span><span class="sxs-lookup"><span data-stu-id="3aed6-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="3aed6-115">通过运行以下命令，使用所需的包（包括 Jupyter Notebook 和 IQ#）来创建和激活新的 conda 环境 `qsharp-env`：</span><span class="sxs-lookup"><span data-stu-id="3aed6-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="3aed6-116">从同一终端运行 `python -c "import qsharp"` 来验证安装项，并用所需的 QDK 组件填充本地包缓存。</span><span class="sxs-lookup"><span data-stu-id="3aed6-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="3aed6-117">使用 .NET CLI 进行安装（高级）</span><span class="sxs-lookup"><span data-stu-id="3aed6-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="3aed6-118">先决条件：</span><span class="sxs-lookup"><span data-stu-id="3aed6-118">Prerequisites:</span></span>

    - <span data-ttu-id="3aed6-119">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3aed6-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="3aed6-120">Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="3aed6-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="3aed6-121">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="3aed6-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="3aed6-122">安装 `Microsoft.Quantum.IQSharp` 包。</span><span class="sxs-lookup"><span data-stu-id="3aed6-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="3aed6-123">如果在 `dotnet iqsharp install` 步骤中遇到错误，请打开新的终端窗口，然后重试。</span><span class="sxs-lookup"><span data-stu-id="3aed6-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="3aed6-124">如果仍有问题，请尝试查找安装的 `dotnet-iqsharp` 工具（在 Windows 上为 `dotnet-iqsharp.exe`）并运行：</span><span class="sxs-lookup"><span data-stu-id="3aed6-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="3aed6-125">其中 `/path/to/dotnet-iqsharp` 应替换为文件系统中 `dotnet-iqsharp` 工具的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="3aed6-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="3aed6-126">通常，该工具在用户配置文件文件夹中的 `.dotnet/tools` 下。</span><span class="sxs-lookup"><span data-stu-id="3aed6-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="3aed6-127">就这么简单！</span><span class="sxs-lookup"><span data-stu-id="3aed6-127">That's it!</span></span> <span data-ttu-id="3aed6-128">你现在有了 Jupyter 的 IQ# 内核，它为用 Q# 来编译和执行 Q# 操作提供了核心功能。</span><span class="sxs-lookup"><span data-stu-id="3aed6-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-q-notebook"></a><span data-ttu-id="3aed6-129">创建你的第一个 Q# 笔记本</span><span class="sxs-lookup"><span data-stu-id="3aed6-129">Create your first Q# notebook</span></span>

<span data-ttu-id="3aed6-130">你现可通过编写和执行简单的 Q# 操作来验证 Q# Jupyter Notebook 安装项。</span><span class="sxs-lookup"><span data-stu-id="3aed6-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and executing a simple Q# operation.</span></span>

1. <span data-ttu-id="3aed6-131">从在安装期间创建的环境（即创建的 conda 环境或安装了 Jupyter 的 Python 环境），运行以下命令来启动 Jupyter Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="3aed6-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="3aed6-132">如果 Jupyter Notebook 未在浏览器中自动打开，请复制命令行提供的 URL 并将其粘贴到浏览器中。</span><span class="sxs-lookup"><span data-stu-id="3aed6-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="3aed6-133">选择“新建”→“Q#”来使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个笔记本单元格：</span><span class="sxs-lookup"><span data-stu-id="3aed6-133">Choose "New" → "Q#" to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="3aed6-134">运行以下笔记本单元格：</span><span class="sxs-lookup"><span data-stu-id="3aed6-134">Run this cell of the notebook:</span></span>

    ![包含 Q# 代码的 Jupyter Notebook 单元格](~/media/install-guide-jupyter.png)

    <span data-ttu-id="3aed6-136">应在单元格的输出中看到 `SampleQuantumRandomNumberGenerator`。</span><span class="sxs-lookup"><span data-stu-id="3aed6-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="3aed6-137">在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且单元格将输出找到的所有操作的名称。</span><span class="sxs-lookup"><span data-stu-id="3aed6-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="3aed6-138">在新单元格中，使用 `%simulate` 命令执行刚刚创建的操作（在模拟器中）：</span><span class="sxs-lookup"><span data-stu-id="3aed6-138">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![包含 %simulate magic 的 Jupyter Notebook 单元格](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="3aed6-140">应会看到所调用的操作的结果。</span><span class="sxs-lookup"><span data-stu-id="3aed6-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="3aed6-141">在本例中，由于操作会生成一个随机结果，因此你将看到屏幕上输出 `Zero` 或 `One`。</span><span class="sxs-lookup"><span data-stu-id="3aed6-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="3aed6-142">如果重复执行该单元格，则每个结果显示的时间大约减半。</span><span class="sxs-lookup"><span data-stu-id="3aed6-142">If you execute the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3aed6-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3aed6-143">Next steps</span></span>

<span data-ttu-id="3aed6-144">你现已安装适用于 Q# Jupyter Notebooks 的 QDK，接下来可在 Jupyter Notebook 环境中直接编写 Q# 代码，从而完成并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="3aed6-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="3aed6-145">要了解更多关于使用 Q# Jupyter Notebook 可以执行的操作的示例，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3aed6-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="3aed6-146">[Q# 和 Jupyter Notebook 简介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="3aed6-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="3aed6-147">你将在这里找到一个 Q# Jupyter Notebook，其中更详细地演示了如何在 Jupyter 环境中使用 Q#。</span><span class="sxs-lookup"><span data-stu-id="3aed6-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="3aed6-148">[Quantum Katas](xref:microsoft.quantum.overview.katas) 是一系列采用 Q# Jupyter Notebook 形式的可自定进度的开放元代码教程和编程练习。</span><span class="sxs-lookup"><span data-stu-id="3aed6-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="3aed6-149">可以先从 [Quantum Katas 教程笔记本](https://github.com/microsoft/QuantumKatas#tutorial-topics)开始。</span><span class="sxs-lookup"><span data-stu-id="3aed6-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="3aed6-150">Quantum Katas 的目标是同时教授量子计算和 Q# 编程的要素。</span><span class="sxs-lookup"><span data-stu-id="3aed6-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="3aed6-151">它们很好地演示了可以使用 Q# Jupyter Notebook 创建哪种内容。</span><span class="sxs-lookup"><span data-stu-id="3aed6-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
