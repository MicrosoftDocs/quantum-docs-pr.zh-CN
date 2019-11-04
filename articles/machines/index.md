---
title: 量子模拟器和主机应用程序 | Microsoft Docs
description: 介绍如何使用经典计算 .NET 语言（通常为 C# 或 Q#）来驱动量子模拟器。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442216"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="5c218-103">量子模拟器和主机应用程序</span><span class="sxs-lookup"><span data-stu-id="5c218-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="5c218-104">学习内容</span><span class="sxs-lookup"><span data-stu-id="5c218-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5c218-105">如何执行量子算法</span><span class="sxs-lookup"><span data-stu-id="5c218-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="5c218-106">此版本中包括哪些量子模拟器</span><span class="sxs-lookup"><span data-stu-id="5c218-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="5c218-107">如何为量子算法编写 C# 驱动程序</span><span class="sxs-lookup"><span data-stu-id="5c218-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="5c218-108">量子开发工具包执行模型</span><span class="sxs-lookup"><span data-stu-id="5c218-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="5c218-109">在[编写量子程序](xref:microsoft.quantum.write-program)时，我们通过将 `QuantumSimulator` 对象传递到算法类的 `Run` 方法来执行量子算法。</span><span class="sxs-lookup"><span data-stu-id="5c218-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="5c218-110">`QuantumSimulator` 类通过完全模拟量子状态向量来执行量子算法，这非常适合用于运行和测试 `Teleport`。</span><span class="sxs-lookup"><span data-stu-id="5c218-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="5c218-111">有关量子状态向量的详细信息，请参阅[概念指南](xref:microsoft.quantum.concepts.intro)。</span><span class="sxs-lookup"><span data-stu-id="5c218-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="5c218-112">其他目标计算机可用于运行量子算法。</span><span class="sxs-lookup"><span data-stu-id="5c218-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="5c218-113">计算机负责为算法提供量子基元的实现。</span><span class="sxs-lookup"><span data-stu-id="5c218-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="5c218-114">其中包括诸如 H、CNOT 和 Measure 等基元操作，以及量子位管理和跟踪。</span><span class="sxs-lookup"><span data-stu-id="5c218-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="5c218-115">不同类的量子机表示相同量子算法的不同执行模型。</span><span class="sxs-lookup"><span data-stu-id="5c218-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="5c218-116">每种类型的量子机可以提供这些基元的不同实现。</span><span class="sxs-lookup"><span data-stu-id="5c218-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="5c218-117">例如，开发工具包中包含的量子计算机跟踪模拟器根本不执行任何模拟。</span><span class="sxs-lookup"><span data-stu-id="5c218-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="5c218-118">而是跟踪算法的量子门、量子位和其他资源使用情况。</span><span class="sxs-lookup"><span data-stu-id="5c218-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="5c218-119">量子机</span><span class="sxs-lookup"><span data-stu-id="5c218-119">Quantum Machines</span></span>

<span data-ttu-id="5c218-120">将来，我们将定义其他量子机类以支持其他类型的模拟，并支持在拓扑量子计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="5c218-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="5c218-121">在改变基础计算机实现的同时允许算法保持不变，可以轻松地在模拟中测试和调试算法，然后在实际硬件上运行该算法，确信该算法没有发生更改。</span><span class="sxs-lookup"><span data-stu-id="5c218-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="5c218-122">此版本中包括的新增功能</span><span class="sxs-lookup"><span data-stu-id="5c218-122">What's Included in this Release</span></span>

<span data-ttu-id="5c218-123">此版本的量子开发人员工具包包含多个量子机类。</span><span class="sxs-lookup"><span data-stu-id="5c218-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="5c218-124">所有类在 `Microsoft.Quantum.Simulation.Simulators` 命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="5c218-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="5c218-125">[完全状态向量模拟器](xref:microsoft.quantum.machines.full-state-simulator)，`QuantumSimulator` 类。</span><span class="sxs-lookup"><span data-stu-id="5c218-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="5c218-126">[简单资源估算器](xref:microsoft.quantum.machines.resources-estimator)，`ResourcesEstimator` 类，它允许对运行量子算法所需的资源进行顶级分析。</span><span class="sxs-lookup"><span data-stu-id="5c218-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="5c218-127">[基于跟踪的资源估算器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)，`QCTraceSimulator` 类，它允许对算法的整个调用关系图的资源消耗量进行高级分析。</span><span class="sxs-lookup"><span data-stu-id="5c218-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="5c218-128">[Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)，`ToffoliSimulator` 类。</span><span class="sxs-lookup"><span data-stu-id="5c218-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="5c218-129">编写主机应用程序</span><span class="sxs-lookup"><span data-stu-id="5c218-129">Writing a host application</span></span>

<span data-ttu-id="5c218-130">在[编写量子程序](xref:microsoft.quantum.write-program)时，我们为传送算法编写简单的 C# 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="5c218-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="5c218-131">C# 驱动程序具有 4 个主要用途：</span><span class="sxs-lookup"><span data-stu-id="5c218-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="5c218-132">构造目标计算机</span><span class="sxs-lookup"><span data-stu-id="5c218-132">Constructing the target machine</span></span>
* <span data-ttu-id="5c218-133">计算量子算法所需的任何参数</span><span class="sxs-lookup"><span data-stu-id="5c218-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="5c218-134">使用模拟器运行量子算法</span><span class="sxs-lookup"><span data-stu-id="5c218-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="5c218-135">处理操作结果</span><span class="sxs-lookup"><span data-stu-id="5c218-135">Processing the result of the operation</span></span>

<span data-ttu-id="5c218-136">下面详细介绍每个步骤。</span><span class="sxs-lookup"><span data-stu-id="5c218-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="5c218-137">构造目标计算机</span><span class="sxs-lookup"><span data-stu-id="5c218-137">Constructing the Target Machine</span></span>

<span data-ttu-id="5c218-138">量子机是普通 .NET 类的实例，因此它们是通过调用其构造函数来创建的，就像任何 .NET 类一样。</span><span class="sxs-lookup"><span data-stu-id="5c218-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="5c218-139">某些模拟器（包括 `QuantumSimulator`）实现 .NET <xref:System.IDisposable?displayProperty=nameWithType> 接口，因此应包装在 C# `using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="5c218-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="5c218-140">计算算法的参数</span><span class="sxs-lookup"><span data-stu-id="5c218-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="5c218-141">在 `Teleport` 示例中，我们计算了要传递给量子算法的一些相对人工参数。</span><span class="sxs-lookup"><span data-stu-id="5c218-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="5c218-142">不过，通常情况下，量子算法需要大量数据，并且最简单的方法是从经典驱动程序提供数据。</span><span class="sxs-lookup"><span data-stu-id="5c218-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="5c218-143">例如，在执行化学模拟时，量子算法需要大量分子轨道交互积分。</span><span class="sxs-lookup"><span data-stu-id="5c218-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="5c218-144">通常，它们是在运行算法时提供的文件中读取的。</span><span class="sxs-lookup"><span data-stu-id="5c218-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="5c218-145">由于 Q# 没有访问文件系统的机制，因此此类数据最好由经典驱动程序收集，然后传递给量子算法的 `Run` 方法。</span><span class="sxs-lookup"><span data-stu-id="5c218-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="5c218-146">经典驱动程序起到重要作用的另一种情况是变分方法。</span><span class="sxs-lookup"><span data-stu-id="5c218-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="5c218-147">在此类算法中，将根据某些经典参数准备好量子状态，并且该状态用于计算感兴趣的某个值。</span><span class="sxs-lookup"><span data-stu-id="5c218-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="5c218-148">根据某种类型的爬山或机器学习算法调整参数，并再次运行量子算法。</span><span class="sxs-lookup"><span data-stu-id="5c218-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="5c218-149">对于此类算法，爬山算法本身最好以经典驱动程序调用的纯经典函数形式实现；然后将爬山的结果传递给量子算法的下一次执行。</span><span class="sxs-lookup"><span data-stu-id="5c218-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="5c218-150">运行量子算法</span><span class="sxs-lookup"><span data-stu-id="5c218-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="5c218-151">此部分通常非常简单。</span><span class="sxs-lookup"><span data-stu-id="5c218-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="5c218-152">每个 Q# 操作都编译为提供静态 `Run` 方法的类。</span><span class="sxs-lookup"><span data-stu-id="5c218-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="5c218-153">此方法的参数由操作本身的平展参数元组以及附加的第一个参数（执行操作所用的模拟器）提供。</span><span class="sxs-lookup"><span data-stu-id="5c218-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="5c218-154">对于需要类型为 `(a: String, (b: Double, c: Double))` 的命名元组的操作，其平展对应类型为 `(String a, Double b, Double c)`。</span><span class="sxs-lookup"><span data-stu-id="5c218-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="5c218-155">向 `Run` 方法传递参数时，有一些细微问题：</span><span class="sxs-lookup"><span data-stu-id="5c218-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="5c218-156">数组必须包装在 `Microsoft.Quantum.Simulation.Core.QArray<T>` 对象中。</span><span class="sxs-lookup"><span data-stu-id="5c218-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="5c218-157">`QArray` 类具有可采用相应对象的任何有序集合 (`IEnumerable<T>`) 的构造函数。</span><span class="sxs-lookup"><span data-stu-id="5c218-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="5c218-158">以 Q# 编写的空元组 `()` 由以 C# 编写的 `QVoid.Instance` 表示。</span><span class="sxs-lookup"><span data-stu-id="5c218-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="5c218-159">非空元组表示为 .NET `ValueTuple` 实例。</span><span class="sxs-lookup"><span data-stu-id="5c218-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="5c218-160">Q# 用户定义的类型作为其基类型传递。</span><span class="sxs-lookup"><span data-stu-id="5c218-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="5c218-161">若要将操作或函数传递到 `Run` 方法，必须使用模拟器的 `Get<>` 方法获取操作或函数的类的实例。</span><span class="sxs-lookup"><span data-stu-id="5c218-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="5c218-162">处理结果</span><span class="sxs-lookup"><span data-stu-id="5c218-162">Processing the Results</span></span>

<span data-ttu-id="5c218-163">从 `Run` 方法返回了量子算法的结果。</span><span class="sxs-lookup"><span data-stu-id="5c218-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="5c218-164">`Run` 方法以异步方式执行，因此它将返回 <xref:System.Threading.Tasks.Task`1> 的实例。</span><span class="sxs-lookup"><span data-stu-id="5c218-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="5c218-165">可以通过多种方法来获取实际操作的结果。</span><span class="sxs-lookup"><span data-stu-id="5c218-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="5c218-166">最简单的方法是使用 `Task` 的 [`Result` 属性](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result)：</span><span class="sxs-lookup"><span data-stu-id="5c218-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="5c218-167">但其他方法（例如，使用 [`Wait` 方法](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait)或 C# [`await` 关键字](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)）也将起作用。</span><span class="sxs-lookup"><span data-stu-id="5c218-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="5c218-168">与参数一样，Q# 元组表示为 `ValueTuple` 实例，Q# 数组表示为 `QArray` 实例。</span><span class="sxs-lookup"><span data-stu-id="5c218-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="5c218-169">用户定义的类型作为其基类型返回。</span><span class="sxs-lookup"><span data-stu-id="5c218-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="5c218-170">空元组 `()` 作为 `QVoid` 类的实例返回。</span><span class="sxs-lookup"><span data-stu-id="5c218-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="5c218-171">许多量子算法需要大量后续处理才能得出有用的答案。</span><span class="sxs-lookup"><span data-stu-id="5c218-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="5c218-172">例如，秀尔算法的量子部分只是找出数字因数的计算的开头。</span><span class="sxs-lookup"><span data-stu-id="5c218-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="5c218-173">在大多数情况下，这是在经典驱动程序中执行此类后续处理的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="5c218-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="5c218-174">只有经典驱动程序才能向用户报告结果或将结果写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="5c218-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="5c218-175">经典驱动程序将有权访问分析库和其他未在 Q# 中公开的数学函数。</span><span class="sxs-lookup"><span data-stu-id="5c218-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="5c218-176">失败数</span><span class="sxs-lookup"><span data-stu-id="5c218-176">Failures</span></span>

<span data-ttu-id="5c218-177">当在执行操作过程中到达 Q# `fail` 语句时，将引发 `ExecutionFailException`。</span><span class="sxs-lookup"><span data-stu-id="5c218-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="5c218-178">由于在 `Run` 方法中使用 `System.Task`，因此由 `fail` 语句引发的异常将包装到 `System.AggregateException` 中。</span><span class="sxs-lookup"><span data-stu-id="5c218-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="5c218-179">若要查找失败的实际原因，需要循环访问 `AggregateException` 
`InnerExceptions`，例如：</span><span class="sxs-lookup"><span data-stu-id="5c218-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="5c218-180">其他经典语言</span><span class="sxs-lookup"><span data-stu-id="5c218-180">Other Classical Languages</span></span>

<span data-ttu-id="5c218-181">虽然我们提供的示例采用 C#、F# 和 Python，但量子开发工具包也支持使用其他语言编写经典主机程序。</span><span class="sxs-lookup"><span data-stu-id="5c218-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="5c218-182">例如，如果你想要在 Visual Basic 中编写主机程序，[应该足以满足需要](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net)。</span><span class="sxs-lookup"><span data-stu-id="5c218-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
