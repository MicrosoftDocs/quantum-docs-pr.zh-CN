---
title: 在 Q 中编写和模拟 qubit 级程序#
description: 有关编写和模拟在单个 qubit 级别运行的量程程序的分步教程
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: 05d3292e1c6e3c8c1163c460f2aaa51c591aa1d5
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422234"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="050ec-103">教程：编写并模拟 qubit 中的程序\#</span><span class="sxs-lookup"><span data-stu-id="050ec-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="050ec-104">欢迎使用量程开发工具包教程，介绍如何编写和模拟在各个 qubits 上运行的基本量程计划。</span><span class="sxs-lookup"><span data-stu-id="050ec-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="050ec-105">尽管 Q # 主要是作为大型的编程语言用于大规模的量程程序，但它也可以轻松地浏览更低级别的量程程序：直接解决特定的 qubits。</span><span class="sxs-lookup"><span data-stu-id="050ec-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="050ec-106">Q # 的灵活性允许用户从任何此类抽象级别中利用量程系统，在本教程中，我们将深入探讨 qubits 本身。</span><span class="sxs-lookup"><span data-stu-id="050ec-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="050ec-107">具体而言，我们将看一下[量程傅立叶转换](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)的组成部分，它是许多更大的量程算法的一个子例程。</span><span class="sxs-lookup"><span data-stu-id="050ec-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="050ec-108">请注意，通常以 "[量程线路](xref:microsoft.quantum.concepts.circuits)" 的形式描述这一低级别的量程信息处理方式，这种方式表示将入口的顺序应用到系统的特定 qubits。</span><span class="sxs-lookup"><span data-stu-id="050ec-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="050ec-109">因此，按顺序应用的单个和多个 qubit 操作可以在 "电路图" 中轻松表示。</span><span class="sxs-lookup"><span data-stu-id="050ec-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="050ec-110">在我们的示例中，我们将定义一个 Q # 操作来执行 qubit 的全部三次傅立叶傅立叶转换，并将以下表示形式作为线路：</span><span class="sxs-lookup"><span data-stu-id="050ec-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="050ec-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="050ec-111">Prerequisites</span></span>

* <span data-ttu-id="050ec-112">使用你首选的语言和开发环境[安装](xref:microsoft.quantum.install)量程开发工具包。</span><span class="sxs-lookup"><span data-stu-id="050ec-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="050ec-113">如果已安装 QDK，请确保将其[更新](xref:microsoft.quantum.update)至最新版本</span><span class="sxs-lookup"><span data-stu-id="050ec-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="050ec-114">本教程介绍以下操作：</span><span class="sxs-lookup"><span data-stu-id="050ec-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="050ec-115">在 Q 中定义量程运算#</span><span class="sxs-lookup"><span data-stu-id="050ec-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="050ec-116">直接从命令行或使用传统主机程序调用 Q # 操作</span><span class="sxs-lookup"><span data-stu-id="050ec-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="050ec-117">模拟从 qubit 分配到测量输出的量程操作</span><span class="sxs-lookup"><span data-stu-id="050ec-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="050ec-118">观察量程系统的模拟 wavefunction 在整个操作过程中的演变方式</span><span class="sxs-lookup"><span data-stu-id="050ec-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="050ec-119">使用 Microsoft 的量程开发工具包运行量程程序通常包括两个部分：</span><span class="sxs-lookup"><span data-stu-id="050ec-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="050ec-120">该程序本身是使用 Q # 量程编程语言实现的，然后调用以在量程计算机或量程模拟器上运行。</span><span class="sxs-lookup"><span data-stu-id="050ec-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="050ec-121">这些包括</span><span class="sxs-lookup"><span data-stu-id="050ec-121">These consist of</span></span> 
    - <span data-ttu-id="050ec-122">Q # 操作：作用于量程寄存器和</span><span class="sxs-lookup"><span data-stu-id="050ec-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="050ec-123">Q # 函数：在量程算法内使用的传统子例程。</span><span class="sxs-lookup"><span data-stu-id="050ec-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="050ec-124">用于调用量程程序并指定应在其上运行该程序的目标计算机的入口点。</span><span class="sxs-lookup"><span data-stu-id="050ec-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="050ec-125">可以直接从命令行执行此操作，也可以通过使用一种传统编程语言（例如 Python 或 c #）编写的主机程序来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="050ec-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="050ec-126">本教程包括你喜欢的任何方法的说明。</span><span class="sxs-lookup"><span data-stu-id="050ec-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="050ec-127">分配 qubits 并定义量程操作</span><span class="sxs-lookup"><span data-stu-id="050ec-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="050ec-128">本教程的第一部分包括定义 Q # 操作 `Perform3qubitQFT` ，该操作在三个 qubits 上执行量程傅立叶转换。</span><span class="sxs-lookup"><span data-stu-id="050ec-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="050ec-129">此外，我们将使用 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 函数来观察三个 qubit 系统的模拟 wavefunction 在整个操作中的发展情况。</span><span class="sxs-lookup"><span data-stu-id="050ec-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="050ec-130">第一步是创建你的 Q # 项目和文件。</span><span class="sxs-lookup"><span data-stu-id="050ec-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="050ec-131">此操作的步骤取决于你将用于调用程序的环境，你可以在相应的[安装指南](xref:microsoft.quantum.install)中找到相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="050ec-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="050ec-132">我们将逐步引导你完成文件的各个组件，但代码还可以作为完整的块提供。</span><span class="sxs-lookup"><span data-stu-id="050ec-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-q-operations"></a><span data-ttu-id="050ec-133">用于访问其他 Q # 操作的命名空间</span><span class="sxs-lookup"><span data-stu-id="050ec-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="050ec-134">在该文件中，我们首先定义 `NamespaceQFT` 将由编译器访问的命名空间。</span><span class="sxs-lookup"><span data-stu-id="050ec-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="050ec-135">为了使我们的操作能够使用现有的 Q # 操作，我们打开了相关的 `Microsoft.Quantum.<>` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="050ec-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="050ec-136">定义具有参数和返回的操作</span><span class="sxs-lookup"><span data-stu-id="050ec-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="050ec-137">接下来，我们定义 `Perform3qubitQFT` 操作：</span><span class="sxs-lookup"><span data-stu-id="050ec-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="050ec-138">现在，此操作不使用任何参数，并且不返回任何内容---在此示例中，我们编写了一个 `Unit` 对象，该对象在 Python 中类似于 `void` c # 或空元组 `Tuple[()]` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="050ec-139">稍后，我们将对其进行修改以返回度量值的数组，此时 `Unit` 将替换该结果 `Result[]` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="050ec-140">将 qubits 分配给`using`</span><span class="sxs-lookup"><span data-stu-id="050ec-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="050ec-141">在我们的 Q # 操作中，我们首先使用以下语句分配三个 qubits 的寄存器 `using` ：</span><span class="sxs-lookup"><span data-stu-id="050ec-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="050ec-142">`using`在中，qubits 会自动分配到 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="050ec-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="050ec-143">我们可以使用和来验证这一点 [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) ，后者将字符串和系统的当前状态打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="050ec-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="050ec-144">`Message(<string>)`和 `DumpMachine()` 函数（ [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) 分别为和）直接打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="050ec-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="050ec-145">就像实际的量程计算一样，Q # 不允许我们直接访问 qubit 状态。</span><span class="sxs-lookup"><span data-stu-id="050ec-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="050ec-146">但是， `DumpMachine` 当打印目标计算机的当前状态时，它可以在与完整状态模拟器结合使用时，为调试和学习提供有价值的见解。</span><span class="sxs-lookup"><span data-stu-id="050ec-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="050ec-147">应用单 qubit 和受控入口</span><span class="sxs-lookup"><span data-stu-id="050ec-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="050ec-148">接下来，应用组成操作本身的入口。</span><span class="sxs-lookup"><span data-stu-id="050ec-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="050ec-149">问 # 已在命名空间中包含许多基本的量程入口作为操作 [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ，并且这些都不是异常。</span><span class="sxs-lookup"><span data-stu-id="050ec-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="050ec-150">在 Q # 操作中，调用 callables 的语句将按顺序执行。</span><span class="sxs-lookup"><span data-stu-id="050ec-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="050ec-151">因此，要应用的第一个入口是 [`H`](xref:microsoft.quantum.intrinsic.h) 第一个 qubit 的（Hadamard）：</span><span class="sxs-lookup"><span data-stu-id="050ec-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="050ec-152">若要将操作应用于寄存器中的特定 qubit （即 `Qubit` 从数组中的单个 `Qubit[]` ），我们使用标准索引表示法。</span><span class="sxs-lookup"><span data-stu-id="050ec-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="050ec-153">因此，将应用 [`H`](xref:microsoft.quantum.intrinsic.h) 到寄存器的第一个 qubit `qs` 将采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="050ec-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="050ec-154">除了将 `H` （Hadamard）入口应用于单个 qubits 外，QFT 线路主要包括受控 [`R1`](xref:microsoft.quantum.intrinsic.r1) 旋转。</span><span class="sxs-lookup"><span data-stu-id="050ec-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="050ec-155">`R1(θ, <qubit>)`通常，操作会保持 qubit 的 $ \ket {0} $ 组件不变，同时应用 $e ^ {i\theta} $ 的旋转到 $ \ket {1} $ 组件。</span><span class="sxs-lookup"><span data-stu-id="050ec-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="050ec-156">受控操作</span><span class="sxs-lookup"><span data-stu-id="050ec-156">Controlled operations</span></span>

<span data-ttu-id="050ec-157">Q # 使在一个或多个控件 qubits 上执行操作的条件非常简单。</span><span class="sxs-lookup"><span data-stu-id="050ec-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="050ec-158">通常，我们只是将调用置于 `Controlled` ，并将操作参数更改为：</span><span class="sxs-lookup"><span data-stu-id="050ec-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="050ec-159">`Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="050ec-160">请注意，控件 qubits 必须作为数组提供，即使它是单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="050ec-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="050ec-161">`H`接下来，我们发现，下一步是在 `R1` 第一个 qubit 上操作（并由第二个/第三个控制）：</span><span class="sxs-lookup"><span data-stu-id="050ec-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="050ec-162">我们称之为</span><span class="sxs-lookup"><span data-stu-id="050ec-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="050ec-163">请注意，我们使用 [`PI()`](xref:microsoft.quantum.math.pi) [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) 命名空间中的函数来定义 pi 弧度的旋转。</span><span class="sxs-lookup"><span data-stu-id="050ec-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="050ec-164">此外，我们将除以 `Double` （例如）， `2.0` 因为除以整数 `2` 将引发类型错误。</span><span class="sxs-lookup"><span data-stu-id="050ec-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="050ec-165">`R1(π/2)`和 `R1(π/4)` 等效于 `S` 和 `T` 操作（也在中 `Microsoft.Quantum.Intrinsic` ）。</span><span class="sxs-lookup"><span data-stu-id="050ec-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="050ec-166">`H`对第二个和第三个 qubits 应用相关操作和受控旋转后：</span><span class="sxs-lookup"><span data-stu-id="050ec-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="050ec-167">我们只需要应用 [`SWAP`](xref:microsoft.quantum.intrinsic.swap) 入口来完成线路：</span><span class="sxs-lookup"><span data-stu-id="050ec-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="050ec-168">这是必需的，因为量程傅立叶转换的性质会按相反的顺序输出 qubits，因此交换允许将子例程无缝集成到更大的算法。</span><span class="sxs-lookup"><span data-stu-id="050ec-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="050ec-169">因此，我们已将量程傅立叶转换的 qubit 级操作写入到 Q # 操作中：</span><span class="sxs-lookup"><span data-stu-id="050ec-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="050ec-170">但是，我们现在不能调用它。</span><span class="sxs-lookup"><span data-stu-id="050ec-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="050ec-171">我们分配的 qubits 是 $ \ket {0} $，在我们分配它们时，在 "问题解答" 中，我们应该按照与我们相同的方式（或更好的方式）来保留。</span><span class="sxs-lookup"><span data-stu-id="050ec-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="050ec-172">解除分配 qubits</span><span class="sxs-lookup"><span data-stu-id="050ec-172">Deallocate qubits</span></span>

<span data-ttu-id="050ec-173">我们 [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) 再次调用来查看操作后状态，最后应用 [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) 于 qubit 注册，以便在完成操作之前将 qubits 重置为 $ \ket {0} $：</span><span class="sxs-lookup"><span data-stu-id="050ec-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="050ec-174">要求将所有释放的 qubits 显式设置为 $ \ket {0} $ 是 Q # 的基本功能，因为当它们开始使用相同的 qubits （一种稀有资源）时，它允许其他操作准确地了解其状态。</span><span class="sxs-lookup"><span data-stu-id="050ec-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="050ec-175">此外，这可确保它们不会与系统中的任何其他 qubits 放大。</span><span class="sxs-lookup"><span data-stu-id="050ec-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="050ec-176">如果在分配块结束时未执行重置 `using` ，则将引发运行时错误。</span><span class="sxs-lookup"><span data-stu-id="050ec-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="050ec-177">完整的 Q # 文件现在应如下所示：</span><span class="sxs-lookup"><span data-stu-id="050ec-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="050ec-178">完成 Q # 文件和操作后，我们的量程计划就可以被调用并进行模拟。</span><span class="sxs-lookup"><span data-stu-id="050ec-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="050ec-179">执行程序</span><span class="sxs-lookup"><span data-stu-id="050ec-179">Execute the program</span></span>

<span data-ttu-id="050ec-180">在文件中定义了 Q # 操作后 `.qs` ，我们现在需要调用该操作并观察返回的任何传统数据。</span><span class="sxs-lookup"><span data-stu-id="050ec-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="050ec-181">目前，没有返回任何内容（回想一下，上面定义的操作返回了 `Unit` ），但当我们稍后修改 Q # 操作来返回测量结果（）的数组时 `Result[]` ，我们将解决此问题。</span><span class="sxs-lookup"><span data-stu-id="050ec-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="050ec-182">尽管 Q # 计划在用于调用它的环境中无处不在，但这样做的方式当然会有所不同。</span><span class="sxs-lookup"><span data-stu-id="050ec-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="050ec-183">因此，只需按照与设置相对应的选项卡中的说明进行操作：使用 Q # 命令行应用程序，或使用 Python 或 c # 中的主机程序。</span><span class="sxs-lookup"><span data-stu-id="050ec-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="050ec-184">命令行</span><span class="sxs-lookup"><span data-stu-id="050ec-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="050ec-185">若要从命令行运行 Q # 程序，只需对 Q # 文件进行少量更改。</span><span class="sxs-lookup"><span data-stu-id="050ec-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="050ec-186">只需在 `@EntryPoint()` 操作定义之前添加一行：</span><span class="sxs-lookup"><span data-stu-id="050ec-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="050ec-187">若要运行程序，请打开项目的文件夹中的终端并输入</span><span class="sxs-lookup"><span data-stu-id="050ec-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="050ec-188">执行时，应会 `Message` `DumpMachine` 在控制台中看到以下输出和输出。</span><span class="sxs-lookup"><span data-stu-id="050ec-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="050ec-189">Python</span><span class="sxs-lookup"><span data-stu-id="050ec-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="050ec-190">创建 Python 主机文件： `host.py` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="050ec-191">主机文件的构造如下所示：</span><span class="sxs-lookup"><span data-stu-id="050ec-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="050ec-192">首先，导入 `qsharp` 模块，该模块将注册 Q # 互操作性的模块加载程序。</span><span class="sxs-lookup"><span data-stu-id="050ec-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="050ec-193">这允许问 # 命名空间（例如 `NamespaceQFT` 我们在 Q # 文件中定义的命名空间）显示为 Python 模块，可以从该模块中导入 q # 操作。</span><span class="sxs-lookup"><span data-stu-id="050ec-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="050ec-194">然后，导入在此示例中将直接调用---的 Q # 操作 `Perform3qubitQFT` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="050ec-195">我们只需要将入口点导入到 Q # 程序（即，_不_是像和这样的操作 `H` `R1` ，而是由其他 Q # 操作调用，而不是由传统主机使用）。</span><span class="sxs-lookup"><span data-stu-id="050ec-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="050ec-196">在模拟 Q # 操作或函数中，使用窗体 `<Q#callable>.simulate(<args>)` 在目标计算机上运行这些操作 `QuantumSimulator()` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="050ec-197">如果我们要在另一台计算机上调用该操作，例如 `ResourceEstimator()` ，只需使用即可 `<Q#callable>.estimate_resources(<args>)` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="050ec-198">通常，Q # 操作对于运行它们的计算机是不可知的，但某些功能（例如）的 `DumpMachine` 行为可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="050ec-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="050ec-199">执行模拟时，操作调用将返回 Q # 文件中定义的值。</span><span class="sxs-lookup"><span data-stu-id="050ec-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="050ec-200">目前没有返回任何内容，但稍后我们将显示分配和处理这些值的示例。</span><span class="sxs-lookup"><span data-stu-id="050ec-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="050ec-201">通过我们的数据和完全传统的结果数据，我们可以执行所需的任何操作。</span><span class="sxs-lookup"><span data-stu-id="050ec-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="050ec-202">你的完整 `host.py` 文件应如下所示：</span><span class="sxs-lookup"><span data-stu-id="050ec-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="050ec-203">运行 Python 文件，并在控制台中打印，应会看到 `Message` `DumpMachine` 以下输出。</span><span class="sxs-lookup"><span data-stu-id="050ec-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="050ec-204">C#</span><span class="sxs-lookup"><span data-stu-id="050ec-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="050ec-205">按照[安装指南](xref:microsoft.quantum.install.cs)中的说明进行操作，创建一个 c # 主机文件，然后将其重命名为 `host.cs` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="050ec-206">C # 宿主有四部分：</span><span class="sxs-lookup"><span data-stu-id="050ec-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="050ec-207">构造量子模拟器。</span><span class="sxs-lookup"><span data-stu-id="050ec-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="050ec-208">在下面的代码中，这是一个变量 `qsim` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="050ec-209">计算量子算法所需的任何参数。</span><span class="sxs-lookup"><span data-stu-id="050ec-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="050ec-210">在此示例中，没有任何内容。</span><span class="sxs-lookup"><span data-stu-id="050ec-210">There are none in this example.</span></span>
3. <span data-ttu-id="050ec-211">运行量子算法。</span><span class="sxs-lookup"><span data-stu-id="050ec-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="050ec-212">每个 Q# 运算都会生成名称相同的 C# 类。</span><span class="sxs-lookup"><span data-stu-id="050ec-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="050ec-213">此类具有“异步”执行运算的 `Run` 方法。</span><span class="sxs-lookup"><span data-stu-id="050ec-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="050ec-214">执行是异步的，因为实际硬件上的执行将是异步的。</span><span class="sxs-lookup"><span data-stu-id="050ec-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="050ec-215">由于 `Run` 方法是异步的，因此我们调用 `Wait()` 方法; 这会阻止执行，直到任务完成并同步返回结果。</span><span class="sxs-lookup"><span data-stu-id="050ec-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="050ec-216">处理返回的操作结果。</span><span class="sxs-lookup"><span data-stu-id="050ec-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="050ec-217">现在，操作不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="050ec-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="050ec-218">运行应用程序，输出应与下面的匹配。</span><span class="sxs-lookup"><span data-stu-id="050ec-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="050ec-219">按下键后，程序将退出。</span><span class="sxs-lookup"><span data-stu-id="050ec-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="050ec-220">在全状态模拟器上调用时， `DumpMachine()` 提供量程状态的 wavefunction 的这些多种表示形式。</span><span class="sxs-lookup"><span data-stu-id="050ec-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="050ec-221">$N $-qubit 系统可能的状态可由 $ 2 ^ n $ 计算基础状态表示，每个状态都具有相应的复杂系数（只是一种振幅和一个阶段）。</span><span class="sxs-lookup"><span data-stu-id="050ec-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="050ec-222">计算基础状态对应于 $n $---长度的所有可能的二进制字符串，即 qubit 状态 $ \ket {0} $ 和 $ \ket $ 的所有可能组合 {1} ，其中每个二进制数字对应于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="050ec-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="050ec-223">第一行提供了一个注释，其中包含相应 qubits 的 Id。</span><span class="sxs-lookup"><span data-stu-id="050ec-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="050ec-224">`2`最重要的是，Qubit 是指在基本状态向量 $ \ket{i} $ 的二进制表示形式中，Qubit 的状态对应于 `2` 最左侧的数字。</span><span class="sxs-lookup"><span data-stu-id="050ec-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="050ec-225">例如，$ \ket {6} = \ket {110} $ 包含 qubits `2` ，以及 $ \ket $ `1` {1} 和 qubit in `0` $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="050ec-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="050ec-226">其余行说明了度量基准状态向量 $ \ket{i} $ 在笛卡尔和极坐标中的概率幅度。</span><span class="sxs-lookup"><span data-stu-id="050ec-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="050ec-227">详细了解输入状态 $ \ket $ 的第一行 {000} ：</span><span class="sxs-lookup"><span data-stu-id="050ec-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="050ec-228">**`|0>:`** 此行对应于 `0` 计算基础状态（假设我们的初始状态为 {000} "\ket $"，我们预计这是在此时具有概率幅度的唯一状态）。</span><span class="sxs-lookup"><span data-stu-id="050ec-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="050ec-229">**`1.000000 +  0.000000 i`**：以笛卡尔格式的概率幅度。</span><span class="sxs-lookup"><span data-stu-id="050ec-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="050ec-230">**` == `**： `equal` 符号分隔等效表示形式。</span><span class="sxs-lookup"><span data-stu-id="050ec-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="050ec-231">**`********************`**：大小的图形表示形式，的数量与 `*` 度量此状态向量的概率成正比。</span><span class="sxs-lookup"><span data-stu-id="050ec-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="050ec-232">**`[ 1.000000 ]`**：量值的数值</span><span class="sxs-lookup"><span data-stu-id="050ec-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="050ec-233">**`    ---`**：振幅阶段的图形化表示形式。</span><span class="sxs-lookup"><span data-stu-id="050ec-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="050ec-234">**`[ 0.0000 rad ]`**：阶段的数值（以弧度为单位）。</span><span class="sxs-lookup"><span data-stu-id="050ec-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="050ec-235">大小和阶段都以图形表示形式显示。</span><span class="sxs-lookup"><span data-stu-id="050ec-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="050ec-236">大小表示形式非常简单：显示一个的条形 `*` ，并显示更大的概率。</span><span class="sxs-lookup"><span data-stu-id="050ec-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="050ec-237">对于阶段，请参阅[测试和调试：](xref:microsoft.quantum.guide.testingdebugging#dump-functions)基于角度范围的可能符号表示形式的转储函数。</span><span class="sxs-lookup"><span data-stu-id="050ec-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="050ec-238">因此，打印输出说明了我们的程控入口从</span><span class="sxs-lookup"><span data-stu-id="050ec-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="050ec-239">$ $ \ket{\psi} \_ {初始} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="050ec-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="050ec-240">to</span><span class="sxs-lookup"><span data-stu-id="050ec-240">to</span></span> 

<span data-ttu-id="050ec-241">$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left （\ket {000} + \ket + {001} \ket {010} + \ket + \ket + {011} {100} \ket {101} + \ket {110} + \ket {111} \right） \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}，\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="050ec-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="050ec-242">这是 qubit 傅立叶转换的确切行为。</span><span class="sxs-lookup"><span data-stu-id="050ec-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="050ec-243">如果你对其他输入状态的影响有了影响，我们建议你在转换前通过应用 qubit 操作来解决。</span><span class="sxs-lookup"><span data-stu-id="050ec-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="050ec-244">添加度量值</span><span class="sxs-lookup"><span data-stu-id="050ec-244">Adding measurements</span></span>

<span data-ttu-id="050ec-245">遗憾的是，量程机制的基石告诉我们，真正的量程系统不能有这样的 `DumpMachine` 功能。</span><span class="sxs-lookup"><span data-stu-id="050ec-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="050ec-246">相反，我们会被迫通过量化指标提取信息，通常情况下，这种情况不仅能提供完整的量程状态，而且还可以显著改变系统本身。</span><span class="sxs-lookup"><span data-stu-id="050ec-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="050ec-247">有很多种类的量程度量，但我们将重点介绍单个 qubits 上的最基本的： projective 度量值。</span><span class="sxs-lookup"><span data-stu-id="050ec-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="050ec-248">根据给定的度量值（例如，计算基础 $ \{ \ket {0} ，\ket {1} \} $），将 qubit 状态投影到衡量的任何基准状态---因此会破坏两者之间的任何 superposition。</span><span class="sxs-lookup"><span data-stu-id="050ec-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="050ec-249">若要在 Q # 计划内实现度量，我们使用的是的 `M` 操作 `Microsoft.Quantum.Intrinsic` ，该操作返回一个 `Result` 类型。</span><span class="sxs-lookup"><span data-stu-id="050ec-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="050ec-250">首先，我们修改 `Perform3QubitQFT` 操作以返回度量结果的数组， `Result[]` 而不是 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="050ec-251">定义和初始化 `Result[]` 数组</span><span class="sxs-lookup"><span data-stu-id="050ec-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="050ec-252">在分配 qubits （即在 `using` 语句之前）之前，我们声明并绑定此数组（ `Result` 每个 qubit 一个）：</span><span class="sxs-lookup"><span data-stu-id="050ec-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="050ec-253">关键字 "靠上" `mutable` `resultArray` 允许稍后在代码中重新绑定变量---例如，添加度量结果时。</span><span class="sxs-lookup"><span data-stu-id="050ec-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="050ec-254">在循环中执行度量 `for` ，并向数组中添加结果</span><span class="sxs-lookup"><span data-stu-id="050ec-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="050ec-255">在块内的 "傅立叶转换" 操作之后 `using` ，插入以下代码：</span><span class="sxs-lookup"><span data-stu-id="050ec-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="050ec-256">[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)在数组上调用的函数（例如，qubits 的数组）将 `qs` 返回数组的索引范围。</span><span class="sxs-lookup"><span data-stu-id="050ec-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="050ec-257">在这里，我们将在循环中使用它， `for` 以按顺序使用语句度量每个 qubit `M(qs[i])` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="050ec-258">然后，将每个测量的 `Result` 类型（ `Zero` 或 `One` ）添加到中的相应索引位置， `resultArray` 并使用更新和重新分配语句。</span><span class="sxs-lookup"><span data-stu-id="050ec-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="050ec-259">此语句的语法对 Q # 是唯一的，但与 `resultArray[i] <- M(qs[i])` 其他语言（如 F # 和 R）中所示的类似变量重新分配相对应。</span><span class="sxs-lookup"><span data-stu-id="050ec-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="050ec-260">关键字 `set` 始终用于重新分配使用绑定 `mutable` 的变量。</span><span class="sxs-lookup"><span data-stu-id="050ec-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="050ec-261">返回`resultArray`</span><span class="sxs-lookup"><span data-stu-id="050ec-261">Return `resultArray`</span></span>

<span data-ttu-id="050ec-262">所有三个 qubits 都得到了度量，并将结果添加到了 `resultArray` 中，我们就可以像以往一样重置和解除分配 qubits。</span><span class="sxs-lookup"><span data-stu-id="050ec-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="050ec-263">`using`块关闭后，插入</span><span class="sxs-lookup"><span data-stu-id="050ec-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="050ec-264">最终返回操作的输出。</span><span class="sxs-lookup"><span data-stu-id="050ec-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="050ec-265">了解度量值的效果</span><span class="sxs-lookup"><span data-stu-id="050ec-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="050ec-266">让我们将函数的位置更改 `DumpMachine` 为在测量前后输出状态。</span><span class="sxs-lookup"><span data-stu-id="050ec-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="050ec-267">最终的操作代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="050ec-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="050ec-268">如果是从命令行运行，则在执行结束时，只会将返回的数组直接打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="050ec-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="050ec-269">否则，请更新主机程序来处理返回的数组。</span><span class="sxs-lookup"><span data-stu-id="050ec-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="050ec-270">命令行</span><span class="sxs-lookup"><span data-stu-id="050ec-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="050ec-271">为了更好地理解将在控制台中打印的返回数组，我们可以 `Message` 在该语句前面的 Q # 文件中添加另一个 `return` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="050ec-272">运行该项目，输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="050ec-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="050ec-273">Python</span><span class="sxs-lookup"><span data-stu-id="050ec-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="050ec-274">将 Python 计划更新为以下内容：</span><span class="sxs-lookup"><span data-stu-id="050ec-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="050ec-275">运行该文件，输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="050ec-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="050ec-276">C#</span><span class="sxs-lookup"><span data-stu-id="050ec-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="050ec-277">现在，我们的操作返回了结果，请将方法调用替换 `Wait()` 为获取 `Result` 属性。</span><span class="sxs-lookup"><span data-stu-id="050ec-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="050ec-278">这仍可实现前面讨论的相同 synchronicity，可以直接将此值绑定到变量 `measurementResult` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="050ec-279">运行该项目，输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="050ec-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="050ec-280">此输出显示了几个不同的内容：</span><span class="sxs-lookup"><span data-stu-id="050ec-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="050ec-281">将返回的结果与预度量值进行比较 `DumpMachine` 时，它_not_清楚地说明了 QFT superposition over 基础状态。</span><span class="sxs-lookup"><span data-stu-id="050ec-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="050ec-282">度量仅返回单基准状态，其概率由系统的 wavefunction 中该状态的幅度决定。</span><span class="sxs-lookup"><span data-stu-id="050ec-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="050ec-283">从下度量值开始 `DumpMachine` ，我们会看到，量化指标_更改_了状态本身，并将其从初始 superposition over 基数状态投影到对应于度量值的单一基准状态。</span><span class="sxs-lookup"><span data-stu-id="050ec-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="050ec-284">如果要重复执行此操作多次，就会看到结果统计信息开始，说明 QFT 状态的 superposition，这会给每个拍摄产生随机结果。</span><span class="sxs-lookup"><span data-stu-id="050ec-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="050ec-285">_不过_，除了效率低下且仍完善，这只会重现基础状态的相对 amplitudes，而不是它们之间的相对阶段。</span><span class="sxs-lookup"><span data-stu-id="050ec-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="050ec-286">在此示例中，后者不是问题，但如果给 QFT 的输入更为复杂，则会看到相对阶段 {000} 。</span><span class="sxs-lookup"><span data-stu-id="050ec-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="050ec-287">部分度量</span><span class="sxs-lookup"><span data-stu-id="050ec-287">Partial measurements</span></span> 
<span data-ttu-id="050ec-288">若要浏览仅测量寄存器的某些 qubits 可能会影响系统状态的方式，请尝试将以下内容添加到循环中的 `for` 测量行之后：</span><span class="sxs-lookup"><span data-stu-id="050ec-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="050ec-289">请注意，若要访问函数，则 `IntAsString` 必须添加</span><span class="sxs-lookup"><span data-stu-id="050ec-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="050ec-290">命名空间语句的其余部分 `open` 。</span><span class="sxs-lookup"><span data-stu-id="050ec-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="050ec-291">在生成的输出中，你将看到逐步投影到 subspaces，因为每个 qubit 都进行了度量。</span><span class="sxs-lookup"><span data-stu-id="050ec-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-q-libraries"></a><span data-ttu-id="050ec-292">使用 Q # 库</span><span class="sxs-lookup"><span data-stu-id="050ec-292">Use the Q# libraries</span></span>
<span data-ttu-id="050ec-293">正如我们在简介中所提到的，很多 Q # 的强大功能都是因为它使您能够抽象掉处理个别 qubits 的问题。</span><span class="sxs-lookup"><span data-stu-id="050ec-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="050ec-294">当然，如果您想要开发完全规模的适用量程程序，请考虑某个操作是 `H` 在特定旋转之前还是之后才会减慢您的速度。</span><span class="sxs-lookup"><span data-stu-id="050ec-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="050ec-295">Q # 库包含[QFT](xref:microsoft.quantum.canon.qft)操作，你可以简单地执行此操作，并将其应用于任意数量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="050ec-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="050ec-296">为此，请在 Q # 文件中定义一个新操作，该操作具有相同的内容 `Perform3QubitQFT` ，但从第一个 `H` 到的内容替换为 `SWAP` 两个简单的行：</span><span class="sxs-lookup"><span data-stu-id="050ec-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="050ec-297">第一行只是创建 [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) qubits 的已分配数组的表达式，即 `qs` [QFT](xref:microsoft.quantum.canon.qft)操作将其作为参数。</span><span class="sxs-lookup"><span data-stu-id="050ec-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="050ec-298">这对应于寄存器中 qubits 的索引排序。</span><span class="sxs-lookup"><span data-stu-id="050ec-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="050ec-299">若要访问这些操作，请 `open` 在 Q # 文件的开头为其各自的命名空间添加语句：</span><span class="sxs-lookup"><span data-stu-id="050ec-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="050ec-300">现在，调整主机程序以调用新操作的名称（例如 `PerformIntrinsicQFT` ），并为其试。</span><span class="sxs-lookup"><span data-stu-id="050ec-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="050ec-301">若要查看使用 Q # 库操作的实际优点，请将 qubits 数改为 `3` 以下值：</span><span class="sxs-lookup"><span data-stu-id="050ec-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="050ec-302">因此，你可以为任何给定数量的 qubits 应用适当的 QFT，而不必担心 `H` 每个 qubit 上的新操作和循环的混乱。</span><span class="sxs-lookup"><span data-stu-id="050ec-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="050ec-303">请注意，在你增加---qubits 的数量时，量程模拟器会以指数方式更长的时间来运行，因为这会使我们期待真实的量程硬件！</span><span class="sxs-lookup"><span data-stu-id="050ec-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













