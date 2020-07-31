---
title: 使用 Q# 和 Python 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 4d148435f01d975e690828dd02335758fc71dfe4
ms.sourcegitcommit: 2f4c637e194dc2b5d18539469ed37444e2800199
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "87436545"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="d3815-102">使用 Q# 和 Python 进行开发</span><span class="sxs-lookup"><span data-stu-id="d3815-102">Develop with Q# and Python</span></span>

<span data-ttu-id="d3815-103">安装用于开发 Python 主机程序的 QDK 以调用 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="d3815-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="d3815-104">安装 `qsharp` Python 包</span><span class="sxs-lookup"><span data-stu-id="d3815-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="d3815-105">使用 conda 进行安装（推荐）</span><span class="sxs-lookup"><span data-stu-id="d3815-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="d3815-106">安装 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。</span><span class="sxs-lookup"><span data-stu-id="d3815-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="d3815-107">**注意：** 需要安装 64 位。</span><span class="sxs-lookup"><span data-stu-id="d3815-107">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="d3815-108">打开 Anaconda 提示。</span><span class="sxs-lookup"><span data-stu-id="d3815-108">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="d3815-109">如果更想要使用 PowerShell 或 pwsh：请打开 shell，运行 `conda init powershell`，然后关闭再重新打开 shell。</span><span class="sxs-lookup"><span data-stu-id="d3815-109">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="d3815-110">通过运行以下命令，使用所需的包（包括 Jupyter Notebook 和 IQ#）来创建和激活新的 conda 环境 `qsharp-env`：</span><span class="sxs-lookup"><span data-stu-id="d3815-110">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="d3815-111">从同一终端运行 `python -c "import qsharp"` 来验证安装项，并用所需的 QDK 组件填充本地包缓存。</span><span class="sxs-lookup"><span data-stu-id="d3815-111">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="d3815-112">使用 .NET CLI 和 pip 进行安装（高级）</span><span class="sxs-lookup"><span data-stu-id="d3815-112">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="d3815-113">先决条件：</span><span class="sxs-lookup"><span data-stu-id="d3815-113">Prerequisites:</span></span>

    - <span data-ttu-id="d3815-114">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d3815-114">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="d3815-115">[PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器</span><span class="sxs-lookup"><span data-stu-id="d3815-115">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="d3815-116">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="d3815-116">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="d3815-117">安装 `qsharp` 包，这是一个可实现 Q# 和 Python 之间互操作的 Python 包。</span><span class="sxs-lookup"><span data-stu-id="d3815-117">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="d3815-118">安装 IQ#，它是 Jupyter 和 Python 使用的内核，提供用于编译和执行 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="d3815-118">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="d3815-119">如果在 `dotnet iqsharp install` 步骤中遇到错误，请打开新的终端窗口，然后重试。</span><span class="sxs-lookup"><span data-stu-id="d3815-119">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="d3815-120">如果仍有问题，请尝试查找安装的 `dotnet-iqsharp` 工具（在 Windows 上为 `dotnet-iqsharp.exe`）并运行：</span><span class="sxs-lookup"><span data-stu-id="d3815-120">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="d3815-121">其中 `/path/to/dotnet-iqsharp` 应替换为文件系统中 `dotnet-iqsharp` 工具的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="d3815-121">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="d3815-122">通常，该工具在用户配置文件文件夹中的 `.dotnet/tools` 下。</span><span class="sxs-lookup"><span data-stu-id="d3815-122">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="d3815-123">就这么简单！</span><span class="sxs-lookup"><span data-stu-id="d3815-123">That's it!</span></span> <span data-ttu-id="d3815-124">你现在有了 `qsharp` Python 包和 Jupyter 的 IQ# 内核，它为用 Python 来编译和执行 Q# 操作提供了核心功能，你还可通过它使用 Q# Jupyter Notebooks。</span><span class="sxs-lookup"><span data-stu-id="d3815-124">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="d3815-125">选择 IDE</span><span class="sxs-lookup"><span data-stu-id="d3815-125">Choose your IDE</span></span>

<span data-ttu-id="d3815-126">虽然可以在任何 IDE 中结合使用 Q# 与 Python，但我们强烈建议为 Q# + Python 应用程序使用 Visual Studio Code (VS Code) IDE。</span><span class="sxs-lookup"><span data-stu-id="d3815-126">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="d3815-127">通过 QDK Visual Studio Code 扩展，你可获得更丰富的功能，例如警告、语法突出显示和项目模板等。</span><span class="sxs-lookup"><span data-stu-id="d3815-127">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="d3815-128">如果想要使用 VS Code：</span><span class="sxs-lookup"><span data-stu-id="d3815-128">If you would like to use VS Code:</span></span>

- <span data-ttu-id="d3815-129">安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）。</span><span class="sxs-lookup"><span data-stu-id="d3815-129">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="d3815-130">安装[适用于 VS Code 的 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="d3815-130">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="d3815-131">如果想要使用其他编辑器，则上述说明都已全部设置好。</span><span class="sxs-lookup"><span data-stu-id="d3815-131">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-q-program"></a><span data-ttu-id="d3815-132">编写你的第一个 Q# 程序</span><span class="sxs-lookup"><span data-stu-id="d3815-132">Write your first Q# program</span></span>

<span data-ttu-id="d3815-133">你现可通过编写和执行简单的 Q# 程序来验证 `qsharp` Python 包安装项。</span><span class="sxs-lookup"><span data-stu-id="d3815-133">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="d3815-134">通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：</span><span class="sxs-lookup"><span data-stu-id="d3815-134">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="d3815-135">在 `Operation.qs` 所在的文件夹中，创建一个名为 `host.py` 的 Python 程序来模拟 Q# `SampleQuantumRandomNumberGenerator()` 操作：</span><span class="sxs-lookup"><span data-stu-id="d3815-135">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="d3815-136">从在安装期间创建的环境（即安装 `qsharp` 的 conda 或 Python 环境），请运行以下程序：</span><span class="sxs-lookup"><span data-stu-id="d3815-136">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="d3815-137">应会看到所调用的操作的结果。</span><span class="sxs-lookup"><span data-stu-id="d3815-137">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="d3815-138">在本例中，由于操作会生成一个随机结果，因此你将看到屏幕上输出 `0` 或 `1`。</span><span class="sxs-lookup"><span data-stu-id="d3815-138">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="d3815-139">如果重复执行该程序，则每个结果显示的时间大约减半。</span><span class="sxs-lookup"><span data-stu-id="d3815-139">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="d3815-140">Python 代码只是普通的 Python 程序。</span><span class="sxs-lookup"><span data-stu-id="d3815-140">The Python code is just a normal Python program.</span></span> <span data-ttu-id="d3815-141">你可使用任何 Python 环境（包括基于 Python 的 Jupyter Notebooks）来编写 Python 程序和调用 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="d3815-141">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="d3815-142">Python 程序可从 Python 代码本身所在的文件夹中的任意 .qs 文件导入 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="d3815-142">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3815-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d3815-143">Next steps</span></span>

<span data-ttu-id="d3815-144">在首选环境中安装量子开发工具包之后，可按照本教程编写并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="d3815-144">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
