---
title: 创建量子随机数生成器
description: 构建一个 Q# 项目，通过创建一个量程随机数生成器来演示 superposition 等基本的量程概念。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8db892091794cb1166e41744572d8938d975abf2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869760"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="eef3f-103">教程：使用 Q# 实现量子随机数生成器\#</span><span class="sxs-lookup"><span data-stu-id="eef3f-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="eef3f-104">用写入的量程算法的一个简单示例 Q# 是量程随机数生成器。</span><span class="sxs-lookup"><span data-stu-id="eef3f-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="eef3f-105">此算法利用量子力学特性来生成随机数。</span><span class="sxs-lookup"><span data-stu-id="eef3f-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eef3f-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="eef3f-106">Prerequisites</span></span>

- <span data-ttu-id="eef3f-107">Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="eef3f-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="eef3f-108">Q#[使用 Q# 从命令行](xref:microsoft.quantum.install.standalone)或使用[Python 主机程序](xref:microsoft.quantum.install.python)或[c # 宿主程序](xref:microsoft.quantum.install.cs)来创建项目。</span><span class="sxs-lookup"><span data-stu-id="eef3f-108">Create a Q# project for either [using Q# from the command line](xref:microsoft.quantum.install.standalone), or with a [Python host program](xref:microsoft.quantum.install.python) or [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-no-locq-operation"></a><span data-ttu-id="eef3f-109">编写 Q# 操作</span><span class="sxs-lookup"><span data-stu-id="eef3f-109">Write a Q# operation</span></span>

### <a name="no-locq-operation-code"></a><span data-ttu-id="eef3f-110">Q#操作代码</span><span class="sxs-lookup"><span data-stu-id="eef3f-110">Q# operation code</span></span>

1. <span data-ttu-id="eef3f-111">将 Program.qs 文件的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="eef3f-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="eef3f-112">如[了解量子计算](xref:microsoft.quantum.overview.understanding)一文中所述，量子比特是可以叠加的量子信息单位。</span><span class="sxs-lookup"><span data-stu-id="eef3f-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="eef3f-113">度量时，量子位只能是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="eef3f-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="eef3f-114">但在执行时，量子位的状态表示进行度量时读取值为 0 或 1 的概率。</span><span class="sxs-lookup"><span data-stu-id="eef3f-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="eef3f-115">此概率状态称为叠加。</span><span class="sxs-lookup"><span data-stu-id="eef3f-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="eef3f-116">我们可以根据此概率生成随机数。</span><span class="sxs-lookup"><span data-stu-id="eef3f-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="eef3f-117">在我们的 Q# 操作中，我们将 `Qubit` 向提供本机数据类型 Q# 。</span><span class="sxs-lookup"><span data-stu-id="eef3f-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="eef3f-118">我们只能通过 `using` 语句来分配 `Qubit`。</span><span class="sxs-lookup"><span data-stu-id="eef3f-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="eef3f-119">分配后，量子位始终处于 `Zero` 状态。</span><span class="sxs-lookup"><span data-stu-id="eef3f-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="eef3f-120">我们可以使用 `H` 操作将 `Qubit` 置于叠加态。</span><span class="sxs-lookup"><span data-stu-id="eef3f-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="eef3f-121">若要度量某个量子位并读取其值，请使用 `M` 内部操作。</span><span class="sxs-lookup"><span data-stu-id="eef3f-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="eef3f-122">将 `Qubit` 置于叠加态并对其进行度量以后，每次调用代码时，我们的结果都会是一个不同值。</span><span class="sxs-lookup"><span data-stu-id="eef3f-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="eef3f-123">取消分配 `Qubit` 时，必须将其显式设置回 `Zero` 状态，否则模拟器会报告运行时错误。</span><span class="sxs-lookup"><span data-stu-id="eef3f-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="eef3f-124">实现此目的的一种简单方法是调用 `Reset`。</span><span class="sxs-lookup"><span data-stu-id="eef3f-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="eef3f-125">使用 Bloch 球将代码可视化</span><span class="sxs-lookup"><span data-stu-id="eef3f-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="eef3f-126">在 Bloch 球中，北极表示经典值 **0**，南极表示经典值 **1**。</span><span class="sxs-lookup"><span data-stu-id="eef3f-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="eef3f-127">任何叠加态都可以用球上的某个点来表示（用箭头表示）。</span><span class="sxs-lookup"><span data-stu-id="eef3f-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="eef3f-128">箭头末端越靠近极点，量子位塌缩成经典值（在度量时分配给该极点）的概率越高。</span><span class="sxs-lookup"><span data-stu-id="eef3f-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="eef3f-129">例如，下面的红色箭头表示的量子位状态在我们度量它时有较高的概率给出值 **0**。</span><span class="sxs-lookup"><span data-stu-id="eef3f-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="eef3f-130">我们可以使用此表示法将代码的功能可视化：</span><span class="sxs-lookup"><span data-stu-id="eef3f-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="eef3f-131">首先，我们起初的量子位初始化为状态 **0**，并且我们应用 `H` 以产生一个叠加态，其中获得 **0** 和 **1** 的概率相同。</span><span class="sxs-lookup"><span data-stu-id="eef3f-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="eef3f-132">然后，我们度量该量子位并保存输出：</span><span class="sxs-lookup"><span data-stu-id="eef3f-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="eef3f-133">由于度量结果是完全随机的，我们获得了一个随机位。</span><span class="sxs-lookup"><span data-stu-id="eef3f-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="eef3f-134">我们可以调用此操作多次来创建多个整数。</span><span class="sxs-lookup"><span data-stu-id="eef3f-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="eef3f-135">例如，如果我们调用此操作三次来获取三个随机位，我们就可以生成随机的 3 位数（即 0 到 7 之间的随机数）。</span><span class="sxs-lookup"><span data-stu-id="eef3f-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="eef3f-136">创建完整的随机数生成器</span><span class="sxs-lookup"><span data-stu-id="eef3f-136">Creating a complete random number generator</span></span>

<span data-ttu-id="eef3f-137">现在，我们有了一个 Q# 生成随机位的操作，可以使用它来生成完整的量程随机数生成器。</span><span class="sxs-lookup"><span data-stu-id="eef3f-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="eef3f-138">我们可以使用 Q# 命令行应用程序或使用主机程序。</span><span class="sxs-lookup"><span data-stu-id="eef3f-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="no-locq-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="eef3f-139">Q#带有 Visual Studio 或 Visual Studio Code 的命令行应用程序</span><span class="sxs-lookup"><span data-stu-id="eef3f-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="eef3f-140">若要创建完整的 Q# 命令行应用程序，请在你的程序中添加以下入口点 Q# ：</span><span class="sxs-lookup"><span data-stu-id="eef3f-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="eef3f-141">可执行文件将在仿真器或资源估计器上运行使用 `@EntryPoint()` 特性标记的操作或函数，具体取决于项目配置和命令行选项。</span><span class="sxs-lookup"><span data-stu-id="eef3f-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="eef3f-142">在 Visual Studio 中，只需按 Ctrl + F5 即可执行该脚本。</span><span class="sxs-lookup"><span data-stu-id="eef3f-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="eef3f-143">在 VS Code 中，通过在终端中键入以下内容来首次生成 Program.qs：</span><span class="sxs-lookup"><span data-stu-id="eef3f-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="eef3f-144">对于后续运行，则无需重新生成它。</span><span class="sxs-lookup"><span data-stu-id="eef3f-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="eef3f-145">若要运行它，请键入以下命令并按 Enter：</span><span class="sxs-lookup"><span data-stu-id="eef3f-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="eef3f-146">在 Visual Studio Code 或命令行中使用 Python</span><span class="sxs-lookup"><span data-stu-id="eef3f-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="eef3f-147">若要 Q# 从 Python 运行新程序，请将以下代码另存为 `host.py` ：</span><span class="sxs-lookup"><span data-stu-id="eef3f-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="eef3f-148">然后便可以从命令行运行 Python 主机程序：</span><span class="sxs-lookup"><span data-stu-id="eef3f-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="eef3f-149">C# 与 Visual Studio Code 或 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eef3f-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="eef3f-150">若要 Q# 从 c # 运行新程序，请修改 `Driver.cs` 以包含以下 c # 代码：</span><span class="sxs-lookup"><span data-stu-id="eef3f-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="eef3f-151">然后，可以从命令行运行 C# 主机程序（在 Visual Studio 中应按 F5）：</span><span class="sxs-lookup"><span data-stu-id="eef3f-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
