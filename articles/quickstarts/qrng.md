---
title: 创建量子随机数生成器
description: 生成一个 Q# 项目，通过创建量子随机数生成器来演示基本的量子概念（例如叠加）。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: d1ad2c1153814e2fa19a38307b2c668c77eae4e3
ms.sourcegitcommit: b7e205aaa7fa1ca9f0daa163e46154945f4bc965
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2020
ms.locfileid: "77441074"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="302d5-103">快速入门：在 Q# 中实现量子随机数生成器</span><span class="sxs-lookup"><span data-stu-id="302d5-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="302d5-104">以 Q# 编写的量子算法的一个简单示例是量子随机数生成器。</span><span class="sxs-lookup"><span data-stu-id="302d5-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="302d5-105">此算法利用量子力学特性来生成随机数。</span><span class="sxs-lookup"><span data-stu-id="302d5-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="302d5-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="302d5-106">Prerequisites</span></span>

- <span data-ttu-id="302d5-107">Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="302d5-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="302d5-108">创建 Q# 项目</span><span class="sxs-lookup"><span data-stu-id="302d5-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="302d5-109">编写 Q# 运算</span><span class="sxs-lookup"><span data-stu-id="302d5-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="302d5-110">Q# 运算代码</span><span class="sxs-lookup"><span data-stu-id="302d5-110">Q# operation code</span></span>

1. <span data-ttu-id="302d5-111">将 Operation.qs 文件的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="302d5-111">Replace the contents of the Operation.qs file with the following code:</span></span>

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

<span data-ttu-id="302d5-112">如 [What is Quantum Computing?](xref:microsoft.quantum.overview.what)（什么是量子计算？）一文所述，量子位是可以处于叠加态的量子信息单元。</span><span class="sxs-lookup"><span data-stu-id="302d5-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="302d5-113">度量时，量子位只能是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="302d5-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="302d5-114">但在执行时，量子位的状态表示进行度量时读取值为 0 或 1 的概率。</span><span class="sxs-lookup"><span data-stu-id="302d5-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="302d5-115">此概率状态称为叠加。</span><span class="sxs-lookup"><span data-stu-id="302d5-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="302d5-116">我们可以根据此概率生成随机数。</span><span class="sxs-lookup"><span data-stu-id="302d5-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="302d5-117">在 Q# 操作中，我们引入了 Q# 原生的 `Qubit` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="302d5-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="302d5-118">我们只能通过 `using` 语句来分配 `Qubit`。</span><span class="sxs-lookup"><span data-stu-id="302d5-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="302d5-119">分配后，量子位始终处于 `Zero` 状态。</span><span class="sxs-lookup"><span data-stu-id="302d5-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="302d5-120">我们可以使用 `H` 操作将 `Qubit` 置于叠加态。</span><span class="sxs-lookup"><span data-stu-id="302d5-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="302d5-121">若要度量某个量子位并读取其值，请使用 `M` 内部操作。</span><span class="sxs-lookup"><span data-stu-id="302d5-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="302d5-122">将 `Qubit` 置于叠加态并对其进行度量以后，每次调用代码时，我们的结果都会是一个不同值。</span><span class="sxs-lookup"><span data-stu-id="302d5-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="302d5-123">取消分配 `Qubit` 时，必须将其显式设置回 `Zero` 状态，否则模拟器会报告运行时错误。</span><span class="sxs-lookup"><span data-stu-id="302d5-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="302d5-124">实现此目的的一种简单方法是调用 `Reset`。</span><span class="sxs-lookup"><span data-stu-id="302d5-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="302d5-125">使用 Bloch 球将代码可视化</span><span class="sxs-lookup"><span data-stu-id="302d5-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="302d5-126">在 Bloch 球中，北极表示经典值 **0**，南极表示经典值 **1**。</span><span class="sxs-lookup"><span data-stu-id="302d5-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="302d5-127">任何叠加态都可以用球上的某个点来表示（用箭头表示）。</span><span class="sxs-lookup"><span data-stu-id="302d5-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="302d5-128">箭头末端越靠近极点，量子位塌缩成经典值（在度量时分配给该极点）的概率越高。</span><span class="sxs-lookup"><span data-stu-id="302d5-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="302d5-129">例如，下面的红色箭头表示的量子位状态在我们度量它时有较高的概率给出值 **0**。</span><span class="sxs-lookup"><span data-stu-id="302d5-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175">

<span data-ttu-id="302d5-130">我们可以使用此表示法将代码的功能可视化：</span><span class="sxs-lookup"><span data-stu-id="302d5-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="302d5-131">首先，我们一开始的量子位初始化为状态 **0**，对其应用 `H` 后会产生一个叠加态，其中获得 **0** 和 **1** 的概率相同。</span><span class="sxs-lookup"><span data-stu-id="302d5-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450">

* <span data-ttu-id="302d5-132">然后，我们度量该量子位并保存输出：</span><span class="sxs-lookup"><span data-stu-id="302d5-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450">

<span data-ttu-id="302d5-133">由于度量结果是完全随机的，我们获得了一个随机位。</span><span class="sxs-lookup"><span data-stu-id="302d5-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="302d5-134">我们可以调用此操作多次来创建多个整数。</span><span class="sxs-lookup"><span data-stu-id="302d5-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="302d5-135">例如，如果我们调用此操作三次来获取三个随机位，我们就可以生成随机的 3 位数（即 0 到 7 之间的随机数）。</span><span class="sxs-lookup"><span data-stu-id="302d5-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="302d5-136">使用主机程序创建完整的随机数生成器</span><span class="sxs-lookup"><span data-stu-id="302d5-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="302d5-137">有了一个生成随机位的 Q# 操作以后，即可使用它通过主机程序构建完整的量子随机数生成器。</span><span class="sxs-lookup"><span data-stu-id="302d5-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="302d5-138">在 Visual Studio Code 或命令行中使用 Python</span><span class="sxs-lookup"><span data-stu-id="302d5-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="302d5-139">要从 Python 运行你的新 Q# 程序，请将以下代码另存为 `host.py`：</span><span class="sxs-lookup"><span data-stu-id="302d5-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="302d5-140">然后便可以从命令行运行 Python 主机程序：</span><span class="sxs-lookup"><span data-stu-id="302d5-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="302d5-141">在 Visual Studio Code 或命令行中使用 C#</span><span class="sxs-lookup"><span data-stu-id="302d5-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="302d5-142">要从 C# 运行你的新 Q# 程序，请修改 `Driver.cs` 以包含以下 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="302d5-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="302d5-143">然后便可以从命令行运行 C# 主机程序：</span><span class="sxs-lookup"><span data-stu-id="302d5-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="302d5-144">在 Visual Studio 2019 中使用 C#</span><span class="sxs-lookup"><span data-stu-id="302d5-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="302d5-145">在 Visual Studio 中，若要通过 C# 运行新的 Q# 程序，请修改 `Driver.cs`，使之包含以下 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="302d5-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="302d5-146">然后按 F5，此时系统就会开始执行程序并弹出一个新窗口，其中包含生成的随机数：</span><span class="sxs-lookup"><span data-stu-id="302d5-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
