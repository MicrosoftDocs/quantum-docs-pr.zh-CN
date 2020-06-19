---
title: 通过 Q# 探索纠缠
description: 了解如何在 Q# 中编写量子程序。 使用 Quantum 开发工具包 (QDK) 开发 Bell 态应用程序
author: natke
ms.author: nakersha
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 271eb7f496835f152573be930d0fe24e59f2d15d
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630076"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="8cd36-104">教程：通过 Q\# 探索纠缠</span><span class="sxs-lookup"><span data-stu-id="8cd36-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="8cd36-105">在本教程中，我们演示如何编写一个 Q# 程序，用于操作和测量量子比特并演示叠加和纠缠效果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="8cd36-106">我们可以据此安装 QDK、生成程序并在量子模拟器上执行该程序。</span><span class="sxs-lookup"><span data-stu-id="8cd36-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="8cd36-107">我们将编写一个用于演示量子纠缠的名为 Bell 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8cd36-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="8cd36-108">Bell 这一名称是指 Bell 状态，即两个量子位的特定量子状态，用于表示叠加和量子纠缠的最简单示例。</span><span class="sxs-lookup"><span data-stu-id="8cd36-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cd36-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="8cd36-109">Prerequisites</span></span>

<span data-ttu-id="8cd36-110">如果准备开始编码，请在继续之前按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8cd36-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="8cd36-111">安装适用于 [Python](xref:microsoft.quantum.install.python) 或 [.NET](xref:microsoft.quantum.install.cs) 的量子开发工具包。</span><span class="sxs-lookup"><span data-stu-id="8cd36-111">Install the Quantum Development Kit for [Python](xref:microsoft.quantum.install.python) or [.NET](xref:microsoft.quantum.install.cs).</span></span>
* <span data-ttu-id="8cd36-112">如果已安装 QDK，请确保将其[更新](xref:microsoft.quantum.update)至最新版本</span><span class="sxs-lookup"><span data-stu-id="8cd36-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="8cd36-113">也可以阅读说明而不安装 QDK，查看 Q# 编程语言的概述和基本的量子计算概念。</span><span class="sxs-lookup"><span data-stu-id="8cd36-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="8cd36-114">使用 Q# 演示量子位行为</span><span class="sxs-lookup"><span data-stu-id="8cd36-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="8cd36-115">回想一下简单的[量子位定义](xref:microsoft.quantum.overview.understanding)。</span><span class="sxs-lookup"><span data-stu-id="8cd36-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="8cd36-116">经典位保存单个二进制值（如 0 或 1），而[量子位](xref:microsoft.quantum.glossary#qubit)的状态则可以是 0 和 1 的**叠加**。</span><span class="sxs-lookup"><span data-stu-id="8cd36-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="8cd36-117">从概念上讲，可以将量子位视为空间中的方向（也称为矢量）。</span><span class="sxs-lookup"><span data-stu-id="8cd36-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="8cd36-118">量子位可以是任何可能的方向。</span><span class="sxs-lookup"><span data-stu-id="8cd36-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="8cd36-119">两个**经典状态**是两个方向，一个方向表示度量结果为 0 的可能性为 100%，另一个方向表示度量结果为 1 的可能性为 100%。</span><span class="sxs-lookup"><span data-stu-id="8cd36-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="8cd36-120">这种表示方式也可通过 [Bloch 球](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)更正式地可视化。</span><span class="sxs-lookup"><span data-stu-id="8cd36-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

<span data-ttu-id="8cd36-121">度量行为会生成二进制结果并改变量子位状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="8cd36-122">度量会生成一个二进制值（0 或 1）。</span><span class="sxs-lookup"><span data-stu-id="8cd36-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="8cd36-123">量子位从叠加态（任何方向）变为经典状态之一。</span><span class="sxs-lookup"><span data-stu-id="8cd36-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="8cd36-124">随后，在没有任何干预操作的情况下重复进行相同的度量会生成相同的二进制结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="8cd36-125">多个量子位可以[**纠缠**](xref:microsoft.quantum.glossary#entanglement)在一起。</span><span class="sxs-lookup"><span data-stu-id="8cd36-125">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span> <span data-ttu-id="8cd36-126">度量一个纠缠的量子位时，就会知道另一个量子位的状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="8cd36-127">现在，我们可以演示如何通过 Q# 来表达这种行为了。</span><span class="sxs-lookup"><span data-stu-id="8cd36-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="8cd36-128">一开始可以编写并生成一个最简单的程序，用于演示量子叠加和量子纠缠。</span><span class="sxs-lookup"><span data-stu-id="8cd36-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="8cd36-129">设置</span><span class="sxs-lookup"><span data-stu-id="8cd36-129">Setup</span></span>

<span data-ttu-id="8cd36-130">本教程使用一个主机程序，并且由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="8cd36-130">This tutorial uses a host programs and consists of two parts:</span></span>

1. <span data-ttu-id="8cd36-131">使用 Q# 量子编程语言实现的一系列量子算法。</span><span class="sxs-lookup"><span data-stu-id="8cd36-131">A series of quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="8cd36-132">使用 Python 或 C# 实现且充当主入口点并调用 Q# 运算来执行量子算法的主机程序。</span><span class="sxs-lookup"><span data-stu-id="8cd36-132">A host program, implemented in either Python or C#, that serves as the main entry point and invokes Q# operations to execute the quantum algorithms.</span></span>

#### <a name="python"></a>[<span data-ttu-id="8cd36-133">Python</span><span class="sxs-lookup"><span data-stu-id="8cd36-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="8cd36-134">为应用程序选择一个位置</span><span class="sxs-lookup"><span data-stu-id="8cd36-134">Choose a location for your application</span></span>

1. <span data-ttu-id="8cd36-135">创建名为 `Bell.qs` 的文件。</span><span class="sxs-lookup"><span data-stu-id="8cd36-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="8cd36-136">此文件将包含你的 Q# 代码。</span><span class="sxs-lookup"><span data-stu-id="8cd36-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="8cd36-137">创建名为 `host.py` 的文件。</span><span class="sxs-lookup"><span data-stu-id="8cd36-137">Create a file called `host.py`.</span></span> <span data-ttu-id="8cd36-138">此文件将包含你的 Python 主机代码。</span><span class="sxs-lookup"><span data-stu-id="8cd36-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="8cd36-139">C# 命令行</span><span class="sxs-lookup"><span data-stu-id="8cd36-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="8cd36-140">创建新的 Q# 项目：</span><span class="sxs-lookup"><span data-stu-id="8cd36-140">Create a new Q# project:</span></span>

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="8cd36-141">你将看到一个 `.csproj` 文件、一个名为 `Operations.qs` 的 Q# 文件，以及一个名为 `Driver.cs` 的主机程序文件</span><span class="sxs-lookup"><span data-stu-id="8cd36-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="8cd36-142">对 Q# 文件重命名</span><span class="sxs-lookup"><span data-stu-id="8cd36-142">Rename the Q# file</span></span>

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="8cd36-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8cd36-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="8cd36-144">创建新项目</span><span class="sxs-lookup"><span data-stu-id="8cd36-144">Create a new project</span></span>

   * <span data-ttu-id="8cd36-145">打开 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8cd36-145">Open Visual Studio</span></span>
   * <span data-ttu-id="8cd36-146">转到“文件”菜单并选择“新建” -> “项目...”  </span><span class="sxs-lookup"><span data-stu-id="8cd36-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="8cd36-147">在项目模板资源管理器的搜索字段中键入 `Q#`，然后选择 `Q# Application` 模板</span><span class="sxs-lookup"><span data-stu-id="8cd36-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="8cd36-148">将项目命名为 `Bell`</span><span class="sxs-lookup"><span data-stu-id="8cd36-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="8cd36-149">对 Q# 文件重命名</span><span class="sxs-lookup"><span data-stu-id="8cd36-149">Rename the Q# file</span></span>

   * <span data-ttu-id="8cd36-150">导航到“解决方案资源管理器”</span><span class="sxs-lookup"><span data-stu-id="8cd36-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="8cd36-151">右键单击 `Operations.qs` 文件</span><span class="sxs-lookup"><span data-stu-id="8cd36-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="8cd36-152">将其重命名为 `Bell.qs`</span><span class="sxs-lookup"><span data-stu-id="8cd36-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="8cd36-153">编写 Q# 运算</span><span class="sxs-lookup"><span data-stu-id="8cd36-153">Write a Q# operation</span></span>

<span data-ttu-id="8cd36-154">我们的目标是准备两个处于特定量子状态的量子位，演示如何通过 Q# 操作量子位，以便更改其状态并演示叠加和纠缠效果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="8cd36-155">我们将逐步完成这一切，以演示量子位状态、操作和度量。</span><span class="sxs-lookup"><span data-stu-id="8cd36-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="8cd36-156">**概述：** 在下面的第一个代码中，我们演示如何在 Q# 中操作量子位。</span><span class="sxs-lookup"><span data-stu-id="8cd36-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="8cd36-157">我们将引入两个操作（`M` 和 `X`）来转换量子位的状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="8cd36-158">在此代码片段中，我们定义了操作 `Set`。该操作使用一个量子位作为参数，使用另一个参数 (`desired`) 来表示我们希望该量子位呈现的状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="8cd36-159">操作 `Set` 使用操作 `M` 对量子位进行度量。</span><span class="sxs-lookup"><span data-stu-id="8cd36-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="8cd36-160">在 Q# 中，量子位的度量始终返回 `Zero` 或 `One`。</span><span class="sxs-lookup"><span data-stu-id="8cd36-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="8cd36-161">如果度量返回的值不等于所需的值，Set 会“翻转”该量子位；也就是说，它会执行 `X` 操作，将量子位状态变为新状态，使度量时返回 `Zero` 和 `One` 的概率反转。</span><span class="sxs-lookup"><span data-stu-id="8cd36-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="8cd36-162">为了演示 `Set` 操作的效果，我们接着添加了 `TestBellState` 操作。</span><span class="sxs-lookup"><span data-stu-id="8cd36-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="8cd36-163">此操作以 `Zero` 或 `One` 作为输入，使用该输入调用 `Set` 操作特定的次数，然后计算对量子位进行度量时返回 `Zero` 的次数和返回 `One` 的次数。</span><span class="sxs-lookup"><span data-stu-id="8cd36-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="8cd36-164">当然，在第一次对 `TestBellState` 操作进行这样的模拟时，我们预期输出会表明：在将 `Zero` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `Zero`；在将 `One` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `One`。</span><span class="sxs-lookup"><span data-stu-id="8cd36-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="8cd36-165">接下来，我们会向 `TestBellState` 添加代码，演示叠加和纠缠。</span><span class="sxs-lookup"><span data-stu-id="8cd36-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="8cd36-166">Q# 运算代码</span><span class="sxs-lookup"><span data-stu-id="8cd36-166">Q# operation code</span></span>

1. <span data-ttu-id="8cd36-167">将 Bell.qs 文件的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="8cd36-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="8cd36-168">现在可以调用此操作，将量子位设置为经典状态：100% 的情况下返回 `Zero`，或者 100% 的情况下返回 `One`。</span><span class="sxs-lookup"><span data-stu-id="8cd36-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="8cd36-169">`Zero` 和 `One` 为常量，表示对量子位进行度量时仅有的两个可能结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="8cd36-170">操作 `Set` 用于度量量子位。</span><span class="sxs-lookup"><span data-stu-id="8cd36-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="8cd36-171">如果量子位处于所需状态，`Set` 会将其保留，否则会执行 `X` 操作，将量子位状态更改为所需状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="8cd36-172">关于 Q# 运算</span><span class="sxs-lookup"><span data-stu-id="8cd36-172">About Q# operations</span></span>

<span data-ttu-id="8cd36-173">Q# 操作是量子子例程。</span><span class="sxs-lookup"><span data-stu-id="8cd36-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="8cd36-174">也就是说，它是一个包含量子操作的可调用例程。</span><span class="sxs-lookup"><span data-stu-id="8cd36-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="8cd36-175">运算的参数在括号内指定为元组。</span><span class="sxs-lookup"><span data-stu-id="8cd36-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="8cd36-176">运算的返回类型在冒号之后指定。</span><span class="sxs-lookup"><span data-stu-id="8cd36-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="8cd36-177">根据这个规则，`Set` 运算表示没有返回类型，因此将标记为返回 `Unit`。</span><span class="sxs-lookup"><span data-stu-id="8cd36-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="8cd36-178">此 Q# 运算等效于 F# 中的 `unit`，大致类似于 C# 中的 `void` 和 Python 中的空元组 (`Tuple[()]`)。</span><span class="sxs-lookup"><span data-stu-id="8cd36-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="8cd36-179">在第一个 Q# 操作中，我们已经使用了两个量子操作：</span><span class="sxs-lookup"><span data-stu-id="8cd36-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="8cd36-180">[M](xref:microsoft.quantum.intrinsic.m) 操作，用于度量量子位的状态</span><span class="sxs-lookup"><span data-stu-id="8cd36-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="8cd36-181">[X](xref:microsoft.quantum.intrinsic.x) 操作，用于翻转量子位的状态</span><span class="sxs-lookup"><span data-stu-id="8cd36-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="8cd36-182">量子操作可转换量子位的状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="8cd36-183">有时候，人们在讨论时会使用与经典“逻辑门”类似的“量子门”（而不是“量子操作”）这一术语。</span><span class="sxs-lookup"><span data-stu-id="8cd36-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="8cd36-184">这种习惯根源于早期的量子计算时代。那时候，算法只是一种理论构造，以图形（类似于经典计算中的线路图）方式表示。</span><span class="sxs-lookup"><span data-stu-id="8cd36-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="8cd36-185">添加 Q# 测试代码</span><span class="sxs-lookup"><span data-stu-id="8cd36-185">Add Q# test code</span></span>

1. <span data-ttu-id="8cd36-186">`Set` 运算结束后，在命名空间内将以下运算添加到 `Bell.qs` 文件：</span><span class="sxs-lookup"><span data-stu-id="8cd36-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="8cd36-187">此运算 (`TestBellState`) 将循环执行 `count` 迭代，在量子位上设置指定的 `initial` 值，然后对结果进行度量 (`M`)。</span><span class="sxs-lookup"><span data-stu-id="8cd36-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="8cd36-188">它将收集我们所度量的 0 和 1 的个数统计信息，并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="8cd36-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="8cd36-189">它执行另一个必需的运算。</span><span class="sxs-lookup"><span data-stu-id="8cd36-189">It performs one other necessary operation.</span></span> <span data-ttu-id="8cd36-190">它将量子位重置为已知状态 (`Zero`)，然后将其返回，使其他人可以在已知状态下分配此量子位。</span><span class="sxs-lookup"><span data-stu-id="8cd36-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="8cd36-191">这是 `using` 语句所必需的。</span><span class="sxs-lookup"><span data-stu-id="8cd36-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="8cd36-192">关于 Q# 中的变量</span><span class="sxs-lookup"><span data-stu-id="8cd36-192">About variables in Q#</span></span>

<span data-ttu-id="8cd36-193">默认情况下，Q# 中的变量是不可变的；它们的值在绑定后将不能更改。</span><span class="sxs-lookup"><span data-stu-id="8cd36-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="8cd36-194">`let` 关键字用于指示不可变变量的绑定。</span><span class="sxs-lookup"><span data-stu-id="8cd36-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="8cd36-195">运算参数始终是不可变的。</span><span class="sxs-lookup"><span data-stu-id="8cd36-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="8cd36-196">如果需要可以更改值的变量（如示例中的 `numOnes`），可以使用 `mutable` 关键字声明该变量。</span><span class="sxs-lookup"><span data-stu-id="8cd36-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="8cd36-197">使用 `set` 语句可以更改可变变量的值。</span><span class="sxs-lookup"><span data-stu-id="8cd36-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="8cd36-198">在这两种情况下，编译器都会推断变量的类型。</span><span class="sxs-lookup"><span data-stu-id="8cd36-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="8cd36-199">Q# 不需要为变量提供任何类型批注。</span><span class="sxs-lookup"><span data-stu-id="8cd36-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="8cd36-200">关于 Q# 中的 `using` 语句</span><span class="sxs-lookup"><span data-stu-id="8cd36-200">About `using` statements in Q#</span></span>

<span data-ttu-id="8cd36-201">Q# 中的 `using` 语句也很特殊。</span><span class="sxs-lookup"><span data-stu-id="8cd36-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="8cd36-202">它用于分配要在代码块中使用的量子位。</span><span class="sxs-lookup"><span data-stu-id="8cd36-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="8cd36-203">在 Q# 中，所有量子位都是动态分配和释放的，而不是在复杂算法的整个生命周期内都存在的固定资源。</span><span class="sxs-lookup"><span data-stu-id="8cd36-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="8cd36-204">`using` 语句在代码块的开头分配一组量子位，并在代码块的末尾释放这些量子位。</span><span class="sxs-lookup"><span data-stu-id="8cd36-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="8cd36-205">创建主机应用程序代码</span><span class="sxs-lookup"><span data-stu-id="8cd36-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="8cd36-206">Python</span><span class="sxs-lookup"><span data-stu-id="8cd36-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="8cd36-207">打开 `host.py` 文件，并添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="8cd36-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="8cd36-208">C#</span><span class="sxs-lookup"><span data-stu-id="8cd36-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="8cd36-209">将 `Driver.cs` 文件的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="8cd36-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="8cd36-210">关于主机应用程序代码</span><span class="sxs-lookup"><span data-stu-id="8cd36-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="8cd36-211">Python</span><span class="sxs-lookup"><span data-stu-id="8cd36-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="8cd36-212">Python 主机应用程序包含三个部分：</span><span class="sxs-lookup"><span data-stu-id="8cd36-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="8cd36-213">计算量子算法所需的任何参数。</span><span class="sxs-lookup"><span data-stu-id="8cd36-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="8cd36-214">在示例中，`count` 固定为 1000，`initial` 是量子位的初始值。</span><span class="sxs-lookup"><span data-stu-id="8cd36-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="8cd36-215">通过调用所导入 Q# 运算的 `simulate()` 方法来运行量子算法。</span><span class="sxs-lookup"><span data-stu-id="8cd36-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="8cd36-216">处理运算结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-216">Process the result of the operation.</span></span> <span data-ttu-id="8cd36-217">在示例中，`res` 接收运算的结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="8cd36-218">此结果是模拟器所度量 0 的个数 (`num_zeros`) 和 1 的个数 (`num_ones`) 的元组。</span><span class="sxs-lookup"><span data-stu-id="8cd36-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="8cd36-219">我们通过析构元组来获取两个字段，然后打印结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="8cd36-220">C#</span><span class="sxs-lookup"><span data-stu-id="8cd36-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="8cd36-221">C# 主机应用程序包含四个部分：</span><span class="sxs-lookup"><span data-stu-id="8cd36-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="8cd36-222">构造量子模拟器。</span><span class="sxs-lookup"><span data-stu-id="8cd36-222">Construct a quantum simulator.</span></span> <span data-ttu-id="8cd36-223">在示例中，`qsim` 是模拟器。</span><span class="sxs-lookup"><span data-stu-id="8cd36-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="8cd36-224">计算量子算法所需的任何参数。</span><span class="sxs-lookup"><span data-stu-id="8cd36-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="8cd36-225">在示例中，`count` 固定为 1000，`initial` 是量子位的初始值。</span><span class="sxs-lookup"><span data-stu-id="8cd36-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="8cd36-226">运行量子算法。</span><span class="sxs-lookup"><span data-stu-id="8cd36-226">Run the quantum algorithm.</span></span> <span data-ttu-id="8cd36-227">每个 Q# 运算都会生成名称相同的 C# 类。</span><span class="sxs-lookup"><span data-stu-id="8cd36-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="8cd36-228">此类具有“异步”执行运算的 `Run` 方法。</span><span class="sxs-lookup"><span data-stu-id="8cd36-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="8cd36-229">执行是异步的，因为实际硬件上的执行将是异步的。</span><span class="sxs-lookup"><span data-stu-id="8cd36-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="8cd36-230">由于 `Run` 方法是异步的，因此我们提取 `Result` 属性；这会阻止执行，直到任务完成并以同步方式返回结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="8cd36-231">处理运算结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-231">Process the result of the operation.</span></span> <span data-ttu-id="8cd36-232">在示例中，`res` 接收运算的结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="8cd36-233">此结果是模拟器所度量 0 的个数 (`numZeros`) 和 1 的个数 (`numOnes`) 的元组。</span><span class="sxs-lookup"><span data-stu-id="8cd36-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="8cd36-234">在 C# 中这会以 ValueTuple 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="8cd36-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="8cd36-235">我们通过析构元组来获取两个字段，打印结果并等待按键。</span><span class="sxs-lookup"><span data-stu-id="8cd36-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="8cd36-236">生成并运行</span><span class="sxs-lookup"><span data-stu-id="8cd36-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="8cd36-237">Python</span><span class="sxs-lookup"><span data-stu-id="8cd36-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="8cd36-238">在终端运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8cd36-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="8cd36-239">此命令将运行模拟 Q# 运算的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="8cd36-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="8cd36-240">结果应为：</span><span class="sxs-lookup"><span data-stu-id="8cd36-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="8cd36-241">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8cd36-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="8cd36-242">在终端运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8cd36-242">Run the following at your terminal:</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="8cd36-243">此命令将自动下载所需的全部包，生成应用程序，然后在命令行中运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="8cd36-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="8cd36-244">或者，按下 F1 打开命令面板，并选择“调试: 在不调试的情况下启动” 。</span><span class="sxs-lookup"><span data-stu-id="8cd36-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="8cd36-245">系统可能会提示你创建新的 ``launch.json`` 文件，以描述如何启动程序。</span><span class="sxs-lookup"><span data-stu-id="8cd36-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="8cd36-246">默认 ``launch.json`` 适用于大多数应用程序。</span><span class="sxs-lookup"><span data-stu-id="8cd36-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="8cd36-247">结果应为：</span><span class="sxs-lookup"><span data-stu-id="8cd36-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="8cd36-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8cd36-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="8cd36-249">只需点击 `F5`，便可生成并运行程序！</span><span class="sxs-lookup"><span data-stu-id="8cd36-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="8cd36-250">结果应为：</span><span class="sxs-lookup"><span data-stu-id="8cd36-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="8cd36-251">按下键后，程序将退出。</span><span class="sxs-lookup"><span data-stu-id="8cd36-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="8cd36-252">准备叠加</span><span class="sxs-lookup"><span data-stu-id="8cd36-252">Prepare superposition</span></span>

<span data-ttu-id="8cd36-253">**概述** 现在，让我们看看 Q# 如何表达将量子位置于叠加态的方式。</span><span class="sxs-lookup"><span data-stu-id="8cd36-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="8cd36-254">回想一下，量子位的状态可以是 0 和 1 的叠加。</span><span class="sxs-lookup"><span data-stu-id="8cd36-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="8cd36-255">为了实现这种叠加，我们将使用 `Hadamard` 操作。</span><span class="sxs-lookup"><span data-stu-id="8cd36-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="8cd36-256">如果量子位处于任一经典状态（度量始终返回 `Zero` 或始终返回 `One`），则 `Hadamard`（简称 `H`）操作会将量子位置于这样一种状态：对量子位进行度量时，50% 的情况下会返回 `Zero`，50% 的情况下会返回 `One`。</span><span class="sxs-lookup"><span data-stu-id="8cd36-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="8cd36-257">从概念上讲，可以将此量子位视为介于 `Zero` 和 `One` 之间的一种中间状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="8cd36-258">现在，我们在模拟 `TestBellState` 操作时会看到度量后的结果会大致返回相等数量的 `Zero` 和 `One`。</span><span class="sxs-lookup"><span data-stu-id="8cd36-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="8cd36-259">首先，我们来尝试翻转量子位（如果量子位为 `Zero` 状态，则会翻转为 `One`，反之亦然）。</span><span class="sxs-lookup"><span data-stu-id="8cd36-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="8cd36-260">操作步骤：先执行 `X` 操作，然后在 `TestBellState` 操作中度量它：</span><span class="sxs-lookup"><span data-stu-id="8cd36-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="8cd36-261">现在结果将翻转（按下 `F5` 后）：</span><span class="sxs-lookup"><span data-stu-id="8cd36-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="8cd36-262">但到目前为止，我们所看到的都是经典运算。</span><span class="sxs-lookup"><span data-stu-id="8cd36-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="8cd36-263">接下来，我们来获取量子结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-263">Let's get a quantum result.</span></span> <span data-ttu-id="8cd36-264">我们需要做的就是将上一个运行中的 `X` 操作替换为 `H`（全称为 Hadamard）操作。</span><span class="sxs-lookup"><span data-stu-id="8cd36-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="8cd36-265">我们不会将所有量子位都从 0 翻转到 1，而是只翻转一半。</span><span class="sxs-lookup"><span data-stu-id="8cd36-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="8cd36-266">`TestBellState` 中的替换行现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="8cd36-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="8cd36-267">现在，结果变得更加有趣：</span><span class="sxs-lookup"><span data-stu-id="8cd36-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="8cd36-268">每次度量状态时，我们都会请求一个经典值，但量子位的 0 和 1 值各占一半，因此从统计学角度而言，我们得到的 0 和 1 各占一半。</span><span class="sxs-lookup"><span data-stu-id="8cd36-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="8cd36-269">这称为“叠加”，它让我们对量子状态有了一个初步的认识。</span><span class="sxs-lookup"><span data-stu-id="8cd36-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="8cd36-270">准备展示纠缠</span><span class="sxs-lookup"><span data-stu-id="8cd36-270">Prepare entanglement</span></span>

<span data-ttu-id="8cd36-271">**概述：** 现在，让我们看看 Q# 如何表达纠缠量子位的方式。</span><span class="sxs-lookup"><span data-stu-id="8cd36-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="8cd36-272">首先，我们将第一个量子位设置为初始状态，然后使用 `H` 操作将其置于叠加状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="8cd36-273">接着，在度量第一个量子位之前，我们使用一个新的操作（`CNOT`，代表“可控非”）。</span><span class="sxs-lookup"><span data-stu-id="8cd36-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="8cd36-274">对两个量子位执行此操作的结果是，在第一个量子位是 `One` 的情况下翻转第二个量子位。</span><span class="sxs-lookup"><span data-stu-id="8cd36-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="8cd36-275">现在，这两个量子位纠缠在一起。</span><span class="sxs-lookup"><span data-stu-id="8cd36-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="8cd36-276">第一个量子位的统计信息没有变化（在度量后，`Zero` 和 `One` 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同。</span><span class="sxs-lookup"><span data-stu-id="8cd36-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="8cd36-277">`CNOT` 把这两个量子位纠缠在了一起，因此，不论其中一个发生什么，另一个也会同样发生。</span><span class="sxs-lookup"><span data-stu-id="8cd36-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="8cd36-278">如果翻转度量值（先翻转第二个量子位，再翻转第一个），会发生相同的情况。</span><span class="sxs-lookup"><span data-stu-id="8cd36-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="8cd36-279">第一个度量值是随机的，第二个将与第一个同步。</span><span class="sxs-lookup"><span data-stu-id="8cd36-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="8cd36-280">我们需要做的第一件事是分配 2 个量子位，而不是在 `TestBellState` 中分配 1 个量子位：</span><span class="sxs-lookup"><span data-stu-id="8cd36-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="8cd36-281">在这种情况下，我们可以先添加一个新操作 (`CNOT`)，再在 `TestBellState` 中度量 (`M`)：</span><span class="sxs-lookup"><span data-stu-id="8cd36-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="8cd36-282">我们还添加了另一个 `Set` 运算，用于初始化第一个量子位，以确保启动时它始终处于 `Zero` 状态。</span><span class="sxs-lookup"><span data-stu-id="8cd36-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="8cd36-283">我们还需要重置第二个量子位，然后再将其释放。</span><span class="sxs-lookup"><span data-stu-id="8cd36-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="8cd36-284">完整的例程现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="8cd36-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="8cd36-285">如果我们运行这段代码，我们将获得与之前相同的 0 和 1 各占一半的结果。</span><span class="sxs-lookup"><span data-stu-id="8cd36-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="8cd36-286">但是，我们想要知道第二个量子位如何响应所度量的第一个量子位。</span><span class="sxs-lookup"><span data-stu-id="8cd36-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="8cd36-287">我们将使用 `TestBellState` 运算的新版本来添加此统计信息：</span><span class="sxs-lookup"><span data-stu-id="8cd36-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="8cd36-288">新的返回值 (`agree`) 会跟踪第一个量子位的度量值与第二个量子位的度量值相同的次数。</span><span class="sxs-lookup"><span data-stu-id="8cd36-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="8cd36-289">我们还需要相应地更新主机应用程序：</span><span class="sxs-lookup"><span data-stu-id="8cd36-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="8cd36-290">Python</span><span class="sxs-lookup"><span data-stu-id="8cd36-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="8cd36-291">C#</span><span class="sxs-lookup"><span data-stu-id="8cd36-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="8cd36-292">现在，运行代码，我们将会得到非常惊人的结果：</span><span class="sxs-lookup"><span data-stu-id="8cd36-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="8cd36-293">如概述中所述，第一个量子位的统计信息没有变化（0 和 1 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同，因为这两个量子位已纠缠在一起！</span><span class="sxs-lookup"><span data-stu-id="8cd36-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="8cd36-294">恭喜，你已经编写了第一个量子程序！</span><span class="sxs-lookup"><span data-stu-id="8cd36-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="next-steps"></a><span data-ttu-id="8cd36-295">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8cd36-295">Next steps</span></span>

<span data-ttu-id="8cd36-296">[Grover 搜索](xref:microsoft.quantum.quickstarts.search)教程介绍了如何生成并运行 Grover 搜索（最常用的量子计算算法之一），并通过一个很好的 Q# 程序示例演示了如何使用量子计算来解决实际问题。</span><span class="sxs-lookup"><span data-stu-id="8cd36-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="8cd36-297">[量子开发工具包入门](xref:microsoft.quantum.welcome)建议了更多的学习 Q# 和量子编程的方法。</span><span class="sxs-lookup"><span data-stu-id="8cd36-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
