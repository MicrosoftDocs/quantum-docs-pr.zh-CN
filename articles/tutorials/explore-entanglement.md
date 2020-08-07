---
title: 探索牵连Q#
description: 了解如何在中编写量程计划 Q# 。 使用 Quantum 开发工具包 (QDK) 开发 Bell 态应用程序
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: c66d26b5ea253d6fc2633fbe52fa35ba703d185d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869692"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="ea857-104">教程：通过 Q\# 探索纠缠</span><span class="sxs-lookup"><span data-stu-id="ea857-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="ea857-105">在本教程中，我们将向您展示如何编写操作 Q# 和测量 qubits 的程序，并演示 superposition 和牵连的影响。</span><span class="sxs-lookup"><span data-stu-id="ea857-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="ea857-106">我们将编写一个用于演示量子纠缠的名为 Bell 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea857-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="ea857-107">Bell 这一名称是指 Bell 状态，即两个量子位的特定量子状态，用于表示叠加和量子纠缠的最简单示例。</span><span class="sxs-lookup"><span data-stu-id="ea857-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="ea857-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="ea857-108">Pre-requisites</span></span>

<span data-ttu-id="ea857-109">如果准备开始编码，请在继续之前按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ea857-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="ea857-110">使用你首选的语言和开发环境[安装](xref:microsoft.quantum.install)量程开发工具包。</span><span class="sxs-lookup"><span data-stu-id="ea857-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="ea857-111">如果已安装 QDK，请确保将其[更新](xref:microsoft.quantum.update)至最新版本</span><span class="sxs-lookup"><span data-stu-id="ea857-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="ea857-112">你还可以遵循这些叙述，无需安装 QDK、查看 Q# 编程语言的概述以及量程计算的第一概念。</span><span class="sxs-lookup"><span data-stu-id="ea857-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="ea857-113">在本教程中，你将学习如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea857-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="ea857-114">在 Q 中创建和合并操作\#</span><span class="sxs-lookup"><span data-stu-id="ea857-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="ea857-115">创建操作，将 qubits 置于 superposition、entangle 中并度量它们。</span><span class="sxs-lookup"><span data-stu-id="ea857-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="ea857-116">演示 Q# 在模拟器中运行的程序的量程牵连。</span><span class="sxs-lookup"><span data-stu-id="ea857-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="ea857-117">通过 QDK 演示 qubit 行为</span><span class="sxs-lookup"><span data-stu-id="ea857-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="ea857-118">经典位保存单个二进制值（如 0 或 1），而[量子位](xref:microsoft.quantum.glossary#qubit)的状态则可以是 0 和 1 的**叠加**。</span><span class="sxs-lookup"><span data-stu-id="ea857-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="ea857-119">从概念上讲，qubit 的状态可以看作是抽象空间中的方向 (也称为矢量) 。</span><span class="sxs-lookup"><span data-stu-id="ea857-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="ea857-120">Qubit 状态可以为任何可能的方向。</span><span class="sxs-lookup"><span data-stu-id="ea857-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="ea857-121">两个**经典状态**是两个方向，一个方向表示度量结果为 0 的可能性为 100%，另一个方向表示度量结果为 1 的可能性为 100%。</span><span class="sxs-lookup"><span data-stu-id="ea857-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="ea857-122">度量行为会生成二进制结果并改变量子位状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="ea857-123">度量值生成一个二进制值，0或1。</span><span class="sxs-lookup"><span data-stu-id="ea857-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="ea857-124">量子位从叠加态（任何方向）变为经典状态之一。</span><span class="sxs-lookup"><span data-stu-id="ea857-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="ea857-125">随后，在没有任何干预操作的情况下重复进行相同的度量会生成相同的二进制结果。</span><span class="sxs-lookup"><span data-stu-id="ea857-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="ea857-126">多个量子位可以[**纠缠**](xref:microsoft.quantum.glossary#entanglement)在一起。</span><span class="sxs-lookup"><span data-stu-id="ea857-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="ea857-127">度量一个纠缠的量子位时，就会知道另一个量子位的状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="ea857-128">现在，我们已准备好演示如何 Q# 表达这一行为。</span><span class="sxs-lookup"><span data-stu-id="ea857-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="ea857-129">一开始可以编写并生成一个最简单的程序，用于演示量子叠加和量子纠缠。</span><span class="sxs-lookup"><span data-stu-id="ea857-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="ea857-130">创建 Q# 项目</span><span class="sxs-lookup"><span data-stu-id="ea857-130">Creating a Q# project</span></span>

<span data-ttu-id="ea857-131">首先，我们要做的就是创建一个新 Q# 项目。</span><span class="sxs-lookup"><span data-stu-id="ea857-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="ea857-132">在本教程中，我们将使用基于[命令行应用程序 VS Code](xref:microsoft.quantum.install.standalone)的环境。</span><span class="sxs-lookup"><span data-stu-id="ea857-132">In this tutorial we are going to use the environment based on [command line applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="ea857-133">若要创建新项目，请在 VS Code 中：</span><span class="sxs-lookup"><span data-stu-id="ea857-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="ea857-134">单击 "**查看**" "  ->  **命令面板**"，然后选择 " \*\* Q# 创建新项目\*\*"。</span><span class="sxs-lookup"><span data-stu-id="ea857-134">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="ea857-135">单击“独立控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="ea857-135">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="ea857-136">导航到项目的保存位置，然后单击“创建项目”。</span><span class="sxs-lookup"><span data-stu-id="ea857-136">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="ea857-137">成功创建项目后，单击右下方的“打开新项目…”。</span><span class="sxs-lookup"><span data-stu-id="ea857-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="ea857-138">在此示例中，我们调用了项目 `Bell` 。</span><span class="sxs-lookup"><span data-stu-id="ea857-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="ea857-139">这会生成两个文件： `Bell.csproj` 、项目文件和 `Program.qs` ，这是 Q# 我们将用于编写应用程序的应用程序模板。</span><span class="sxs-lookup"><span data-stu-id="ea857-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="ea857-140">的内容 `Program.qs` 应为：</span><span class="sxs-lookup"><span data-stu-id="ea857-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="ea857-141">编写 Q \# 应用程序</span><span class="sxs-lookup"><span data-stu-id="ea857-141">Write the Q\# application</span></span>
 
<span data-ttu-id="ea857-142">我们的目标是在特定的量程状态下准备两个 qubits，演示如何在 qubits 上操作 Q# 以更改其状态，并演示 superposition 和牵连的效果。</span><span class="sxs-lookup"><span data-stu-id="ea857-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="ea857-143">我们将构建这一段内容，以引入 qubit 状态、操作和度量。</span><span class="sxs-lookup"><span data-stu-id="ea857-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="ea857-144">使用度量值初始化 qubit</span><span class="sxs-lookup"><span data-stu-id="ea857-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="ea857-145">下面的第一个代码介绍了如何在中使用 qubits Q# 。</span><span class="sxs-lookup"><span data-stu-id="ea857-145">In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="ea857-146">我们将介绍两个操作，这些操作将 [`M`](xref:microsoft.quantum.intrinsic.m) [`X`](xref:microsoft.quantum.intrinsic.x) 转换 qubit 的状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-146">We’ll introduce two operations, [`M`](xref:microsoft.quantum.intrinsic.m) and [`X`](xref:microsoft.quantum.intrinsic.x) that transform the state of a qubit.</span></span> <span data-ttu-id="ea857-147">在此代码片段中，我们定义了操作 `SetQubitState`。该操作使用一个量子位作为参数，使用另一个参数 (`desired`) 来表示我们希望该量子位呈现的状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="ea857-148">操作 `SetQubitState` 使用操作 `M` 对量子位进行度量。</span><span class="sxs-lookup"><span data-stu-id="ea857-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="ea857-149">在中 Q# ，qubit 度量值始终返回 `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="ea857-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="ea857-150">如果度量值返回一个不等于所需值的值，则 `SetQubitState` "翻转" qubit; 也就是说，它将执行一个 `X` 操作，该操作会将 qubit 状态更改为一种新状态，在该状态下，测量的概率返回 `Zero` 并 `One` 反转。</span><span class="sxs-lookup"><span data-stu-id="ea857-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="ea857-151">这样，就 `SetQubitState` 始终将目标 qubit 置于所需状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="ea857-152">将的内容替换为 `Program.qs` 以下代码：</span><span class="sxs-lookup"><span data-stu-id="ea857-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="ea857-153">现在可以调用此操作，将量子位设置为经典状态：100% 的情况下返回 `Zero`，或者 100% 的情况下返回 `One`。</span><span class="sxs-lookup"><span data-stu-id="ea857-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="ea857-154">`Zero` 和 `One` 为常量，表示对量子位进行度量时仅有的两个可能结果。</span><span class="sxs-lookup"><span data-stu-id="ea857-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="ea857-155">操作 `SetQubitState` 用于度量量子位。</span><span class="sxs-lookup"><span data-stu-id="ea857-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="ea857-156">如果量子位处于所需状态，`SetQubitState` 会将其保留，否则会执行 `X` 操作，将量子位状态更改为所需状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="ea857-157">关于 Q# 操作</span><span class="sxs-lookup"><span data-stu-id="ea857-157">About Q# operations</span></span>

<span data-ttu-id="ea857-158">Q#操作是一个量程子例程。</span><span class="sxs-lookup"><span data-stu-id="ea857-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="ea857-159">也就是说，它是包含对其他量程操作的调用的可调用例程。</span><span class="sxs-lookup"><span data-stu-id="ea857-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="ea857-160">运算的参数在括号内指定为元组。</span><span class="sxs-lookup"><span data-stu-id="ea857-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="ea857-161">运算的返回类型在冒号之后指定。</span><span class="sxs-lookup"><span data-stu-id="ea857-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="ea857-162">根据这个规则，`SetQubitState` 运算表示没有返回类型，因此将标记为返回 `Unit`。</span><span class="sxs-lookup"><span data-stu-id="ea857-162">In this case, the `SetQubitState` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="ea857-163">这是 Q# `unit` F # 中的等效项，它大致类似于 `void` c # 中的，空元组 (`Tuple[()]` 在 Python 中) 。</span><span class="sxs-lookup"><span data-stu-id="ea857-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="ea857-164">您在第一次操作中使用了两个量程操作 Q# ：</span><span class="sxs-lookup"><span data-stu-id="ea857-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="ea857-165">[`M`](xref:microsoft.quantum.intrinsic.m)操作，它测量 qubit 的状态</span><span class="sxs-lookup"><span data-stu-id="ea857-165">The [`M`](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="ea857-166">[`X`](xref:microsoft.quantum.intrinsic.x)操作，该操作将反转 qubit 的状态</span><span class="sxs-lookup"><span data-stu-id="ea857-166">The [`X`](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="ea857-167">量子操作可转换量子位的状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="ea857-168">有时候，人们在讨论时会使用与经典“逻辑门”类似的“量子门”（而不是“量子操作”）这一术语。</span><span class="sxs-lookup"><span data-stu-id="ea857-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="ea857-169">这种习惯根源于早期的量子计算时代。那时候，算法只是一种理论构造，以图形（类似于经典计算中的线路图）方式表示。</span><span class="sxs-lookup"><span data-stu-id="ea857-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="ea857-170">统计度量结果</span><span class="sxs-lookup"><span data-stu-id="ea857-170">Counting measurement outcomes</span></span>

<span data-ttu-id="ea857-171">为了演示 `SetQubitState` 操作的效果，我们接着添加了 `TestBellState` 操作。</span><span class="sxs-lookup"><span data-stu-id="ea857-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="ea857-172">此操作以 `Zero` 或 `One` 作为输入，使用该输入调用 `SetQubitState` 操作特定的次数，然后计算对量子位进行度量时返回 `Zero` 的次数和返回 `One` 的次数。</span><span class="sxs-lookup"><span data-stu-id="ea857-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="ea857-173">当然，在第一次对 `TestBellState` 操作进行这样的模拟时，我们预期输出会表明：在将 `Zero` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `Zero`；在将 `One` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `One`。</span><span class="sxs-lookup"><span data-stu-id="ea857-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="ea857-174">接下来，我们将向 `TestBellState` 演示 superposition 和牵连添加代码。</span><span class="sxs-lookup"><span data-stu-id="ea857-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="ea857-175">`SetQubitState` 运算结束后，在命名空间内将以下运算添加到 `Bell.qs` 文件：</span><span class="sxs-lookup"><span data-stu-id="ea857-175">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="ea857-176">请注意，我们在中添加了一条线， `return` 以便在控制台中打印一条说明性消息，其中包含函数 (`Message`) []</span><span class="sxs-lookup"><span data-stu-id="ea857-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="ea857-177">此运算 (`TestBellState`) 将循环执行 `count` 迭代，在量子位上设置指定的 `initial` 值，然后对结果进行度量 (`M`)。</span><span class="sxs-lookup"><span data-stu-id="ea857-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="ea857-178">它将收集我们所度量的 0 和 1 的个数统计信息，并将其返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="ea857-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="ea857-179">它执行另一个必需的运算。</span><span class="sxs-lookup"><span data-stu-id="ea857-179">It performs one other necessary operation.</span></span> <span data-ttu-id="ea857-180">它将量子位重置为已知状态 (`Zero`)，然后将其返回，使其他人可以在已知状态下分配此量子位。</span><span class="sxs-lookup"><span data-stu-id="ea857-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="ea857-181">这是 `using` 语句所必需的。</span><span class="sxs-lookup"><span data-stu-id="ea857-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="ea857-182">关于 Q 中的变量\#</span><span class="sxs-lookup"><span data-stu-id="ea857-182">About variables in Q\#</span></span>

<span data-ttu-id="ea857-183">默认情况下，中的变量 Q# 是不可变的; 它们的值在绑定后可能不会更改。</span><span class="sxs-lookup"><span data-stu-id="ea857-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="ea857-184">`let` 关键字用于指示不可变变量的绑定。</span><span class="sxs-lookup"><span data-stu-id="ea857-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="ea857-185">运算参数始终是不可变的。</span><span class="sxs-lookup"><span data-stu-id="ea857-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="ea857-186">如果需要可以更改值的变量（如示例中的 `numOnes`），可以使用 `mutable` 关键字声明该变量。</span><span class="sxs-lookup"><span data-stu-id="ea857-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="ea857-187">使用 `setQubitState` 语句可以更改可变变量的值。</span><span class="sxs-lookup"><span data-stu-id="ea857-187">A mutable variable's value may be changed using a `setQubitState` statement.</span></span>

<span data-ttu-id="ea857-188">在这两种情况下，编译器都会推断变量的类型。</span><span class="sxs-lookup"><span data-stu-id="ea857-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="ea857-189">Q#不需要任何变量的类型批注。</span><span class="sxs-lookup"><span data-stu-id="ea857-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="ea857-190">`using`问答中的语句\#</span><span class="sxs-lookup"><span data-stu-id="ea857-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="ea857-191">`using`语句也是特殊的 Q# 。</span><span class="sxs-lookup"><span data-stu-id="ea857-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="ea857-192">它用于分配要在代码块中使用的量子位。</span><span class="sxs-lookup"><span data-stu-id="ea857-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="ea857-193">在中 Q# ，所有 qubits 都是动态分配和释放的，而不是固定在复杂算法的整个生存期内的资源。</span><span class="sxs-lookup"><span data-stu-id="ea857-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="ea857-194">`using` 语句在代码块的开头分配一组量子位，并在代码块的末尾释放这些量子位。</span><span class="sxs-lookup"><span data-stu-id="ea857-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="execute-the-code-from-the-command-line"></a><span data-ttu-id="ea857-195">从命令行执行代码</span><span class="sxs-lookup"><span data-stu-id="ea857-195">Execute the code from the command line</span></span>

<span data-ttu-id="ea857-196">若要运行代码，我们需要指定在提供命令时要*运行的可调用的*编译器 `dotnet run` 。</span><span class="sxs-lookup"><span data-stu-id="ea857-196">In order to run the code we need to specify the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="ea857-197">此操作 Q# 通过在此情况下添加一行，并在 `@EntryPoint()` `TestBellState` 此示例中添加一行，在文件中进行简单的更改。</span><span class="sxs-lookup"><span data-stu-id="ea857-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="ea857-198">完整的代码应为：</span><span class="sxs-lookup"><span data-stu-id="ea857-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="ea857-199">若要运行程序，我们需要 `count` `initial` 从命令行指定和参数。</span><span class="sxs-lookup"><span data-stu-id="ea857-199">To run the program we need to specify `count` and `initial` arguments from the command line.</span></span> <span data-ttu-id="ea857-200">选择例如 `count = 1000` 和 `initial = One` 。</span><span class="sxs-lookup"><span data-stu-id="ea857-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="ea857-201">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ea857-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="ea857-202">你应看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="ea857-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="ea857-203">如果尝试执行此 `initial = Zero` 操作，应注意：</span><span class="sxs-lookup"><span data-stu-id="ea857-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="ea857-204">准备叠加</span><span class="sxs-lookup"><span data-stu-id="ea857-204">Prepare superposition</span></span>

<span data-ttu-id="ea857-205">现在让我们看看如何 Q# 在 superposition 中表达 qubits 的方式。</span><span class="sxs-lookup"><span data-stu-id="ea857-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="ea857-206">回想一下，量子位的状态可以是 0 和 1 的叠加。</span><span class="sxs-lookup"><span data-stu-id="ea857-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="ea857-207">为了实现这种叠加，我们将使用 `Hadamard` 操作。</span><span class="sxs-lookup"><span data-stu-id="ea857-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="ea857-208">如果量子位处于任一经典状态（度量始终返回 `Zero` 或始终返回 `One`），则 `Hadamard`（简称 `H`）操作会将量子位置于这样一种状态：对量子位进行度量时，50% 的情况下会返回 `Zero`，50% 的情况下会返回 `One`。</span><span class="sxs-lookup"><span data-stu-id="ea857-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="ea857-209">从概念上讲，可以将此量子位视为介于 `Zero` 和 `One` 之间的一种中间状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="ea857-210">现在，我们在模拟 `TestBellState` 操作时会看到度量后的结果会大致返回相等数量的 `Zero` 和 `One`。</span><span class="sxs-lookup"><span data-stu-id="ea857-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="ea857-211">`X`翻转 qubit 状态</span><span class="sxs-lookup"><span data-stu-id="ea857-211">`X` flips qubit state</span></span>

<span data-ttu-id="ea857-212">首先，我们来尝试翻转量子位（如果量子位为 `Zero` 状态，则会翻转为 `One`，反之亦然）。</span><span class="sxs-lookup"><span data-stu-id="ea857-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="ea857-213">操作步骤：先执行 `X` 操作，然后在 `TestBellState` 操作中度量它：</span><span class="sxs-lookup"><span data-stu-id="ea857-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="ea857-214">现在会反转结果：</span><span class="sxs-lookup"><span data-stu-id="ea857-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="ea857-215">现在，让我们探索 qubits 的量程属性。</span><span class="sxs-lookup"><span data-stu-id="ea857-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="ea857-216">`H`准备 superposition</span><span class="sxs-lookup"><span data-stu-id="ea857-216">`H` prepares superposition</span></span>

<span data-ttu-id="ea857-217">我们需要做的就是将上一个运行中的 `X` 操作替换为 `H`（全称为 Hadamard）操作。</span><span class="sxs-lookup"><span data-stu-id="ea857-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="ea857-218">我们不会将所有量子位都从 0 翻转到 1，而是只翻转一半。</span><span class="sxs-lookup"><span data-stu-id="ea857-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="ea857-219">`TestBellState` 中的替换行现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea857-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="ea857-220">现在，结果变得更加有趣：</span><span class="sxs-lookup"><span data-stu-id="ea857-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="ea857-221">每次度量状态时，我们都会请求一个经典值，但量子位的 0 和 1 值各占一半，因此从统计学角度而言，我们得到的 0 和 1 各占一半。</span><span class="sxs-lookup"><span data-stu-id="ea857-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="ea857-222">这称为“叠加”，它让我们对量子状态有了一个初步的认识。</span><span class="sxs-lookup"><span data-stu-id="ea857-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="ea857-223">准备展示纠缠</span><span class="sxs-lookup"><span data-stu-id="ea857-223">Prepare entanglement</span></span>

<span data-ttu-id="ea857-224">现在让我们看看如何 Q# 表达 entangle qubits 的方法。</span><span class="sxs-lookup"><span data-stu-id="ea857-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="ea857-225">首先，我们将第一个量子位设置为初始状态，然后使用 `H` 操作将其置于叠加状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="ea857-226">然后，在度量第一个 qubit 之前，我们使用 () 的新操作 `CNOT` ，该操作代表受控-NOT。</span><span class="sxs-lookup"><span data-stu-id="ea857-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-NOT.</span></span>  <span data-ttu-id="ea857-227">对两个量子位执行此操作的结果是，在第一个量子位是 `One` 的情况下翻转第二个量子位。</span><span class="sxs-lookup"><span data-stu-id="ea857-227">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="ea857-228">现在，这两个量子位纠缠在一起。</span><span class="sxs-lookup"><span data-stu-id="ea857-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="ea857-229">第一个量子位的统计信息没有变化（在度量后，`Zero` 和 `One` 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同。</span><span class="sxs-lookup"><span data-stu-id="ea857-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="ea857-230">`CNOT` 把这两个量子位纠缠在了一起，因此，不论其中一个发生什么，另一个也会同样发生。</span><span class="sxs-lookup"><span data-stu-id="ea857-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="ea857-231">如果翻转度量值（先翻转第二个量子位，再翻转第一个），会发生相同的情况。</span><span class="sxs-lookup"><span data-stu-id="ea857-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="ea857-232">第一个度量值是随机的，第二个将与第一个同步。</span><span class="sxs-lookup"><span data-stu-id="ea857-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="ea857-233">我们需要做的第一件事就是在中分配两个 qubits，而不是一个 `TestBellState` ：</span><span class="sxs-lookup"><span data-stu-id="ea857-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="ea857-234">在这种情况下，我们可以先添加一个新操作 (`CNOT`)，再在 `TestBellState` 中度量 (`M`)：</span><span class="sxs-lookup"><span data-stu-id="ea857-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="ea857-235">我们还添加了另一个 `SetQubitState` 运算，用于初始化第一个量子位，以确保启动时它始终处于 `Zero` 状态。</span><span class="sxs-lookup"><span data-stu-id="ea857-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="ea857-236">我们还需要重置第二个量子位，然后再将其释放。</span><span class="sxs-lookup"><span data-stu-id="ea857-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="ea857-237">完整的例程现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea857-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="ea857-238">如果我们运行这段代码，我们将获得与之前相同的 0 和 1 各占一半的结果。</span><span class="sxs-lookup"><span data-stu-id="ea857-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="ea857-239">但是，我们想要知道第二个量子位如何响应所度量的第一个量子位。</span><span class="sxs-lookup"><span data-stu-id="ea857-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="ea857-240">我们将使用 `TestBellState` 运算的新版本来添加此统计信息：</span><span class="sxs-lookup"><span data-stu-id="ea857-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="ea857-241">新的返回值 (`agree`) 会跟踪第一个量子位的度量值与第二个量子位的度量值相同的次数。</span><span class="sxs-lookup"><span data-stu-id="ea857-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="ea857-242">运行我们获得的代码：</span><span class="sxs-lookup"><span data-stu-id="ea857-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="ea857-243">如概述中所述，第一个量子位的统计信息没有变化（0 和 1 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同，因为这两个量子位已纠缠在一起！</span><span class="sxs-lookup"><span data-stu-id="ea857-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="ea857-244">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ea857-244">Next steps</span></span>

<span data-ttu-id="ea857-245">教程[Grover 的搜索](xref:microsoft.quantum.quickstarts.search)介绍了如何生成和运行 Grover 搜索，这是最常用的一种量程计算算法，提供了一个 Q# 可用于解决量程计算的真正问题的程序示例。</span><span class="sxs-lookup"><span data-stu-id="ea857-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="ea857-246">[量程开发工具包入门建议了](xref:microsoft.quantum.welcome)更多学习 Q# 和量程编程的方法。</span><span class="sxs-lookup"><span data-stu-id="ea857-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
