---
title: 运行程序的方式 Q#
description: 运行程序的不同方法的概述 Q# 。 Q#在 Python 或 .net 语言的命令提示符下，Jupyter 笔记本和经典主机程序。
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231683"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="227c9-104">运行程序的方式 Q#</span><span class="sxs-lookup"><span data-stu-id="227c9-104">Ways to run a Q# program</span></span>

<span data-ttu-id="227c9-105">量程开发工具包的最大优势之一是其跨平台和开发环境的灵活性。</span><span class="sxs-lookup"><span data-stu-id="227c9-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="227c9-106">但是，这也意味着，新 Q# 用户可能会发现，在 [安装指南](xref:microsoft.quantum.install)中找到的众多选项可能会混淆或淹没。</span><span class="sxs-lookup"><span data-stu-id="227c9-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="227c9-107">在此页上，我们将介绍运行程序时所发生的情况 Q# ，并比较用户可执行此操作的不同方式。</span><span class="sxs-lookup"><span data-stu-id="227c9-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="227c9-108">主要区别在于， Q# 可以运行：</span><span class="sxs-lookup"><span data-stu-id="227c9-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="227c9-109">作为独立的应用程序，其中 Q# 是所涉及的唯一语言，直接调用程序。</span><span class="sxs-lookup"><span data-stu-id="227c9-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="227c9-110">这两种方法实际上属于此类别：</span><span class="sxs-lookup"><span data-stu-id="227c9-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="227c9-111">命令行接口</span><span class="sxs-lookup"><span data-stu-id="227c9-111">the command-line interface</span></span>
  - <span data-ttu-id="227c9-112">Q# Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="227c9-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="227c9-113">使用其他 *主机程序*（以 Python 或 .net 语言编写） (例如，c # 或 F # ) ，然后调用程序并可以进一步处理返回的结果。</span><span class="sxs-lookup"><span data-stu-id="227c9-113">with an additional *host program*, written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="227c9-114">为了更好地了解这些过程及其区别，我们考虑了一个简单的 Q# 程序并对其运行方式进行比较。</span><span class="sxs-lookup"><span data-stu-id="227c9-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="227c9-115">基本 Q# 计划</span><span class="sxs-lookup"><span data-stu-id="227c9-115">Basic Q# program</span></span>

<span data-ttu-id="227c9-116">基本的量程计划可能包含：在状态 $ \ket {0} $ 和 $ \ket $ 的 superposition 中准备 qubit {1} ，对其进行度量，并返回结果，这两种状态将随机成为具有相同概率的两种状态之一。</span><span class="sxs-lookup"><span data-stu-id="227c9-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="227c9-117">事实上，此过程是 [量程随机数生成器](xref:microsoft.quantum.quickstarts.qrng) 快速入门的核心。</span><span class="sxs-lookup"><span data-stu-id="227c9-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="227c9-118">在中 Q# ，这将由以下代码执行：</span><span class="sxs-lookup"><span data-stu-id="227c9-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="227c9-119">但是，此代码本身不能由运行 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-119">However, this code alone can't be run by Q#.</span></span>
<span data-ttu-id="227c9-120">为此，它需要构成 [操作](xref:microsoft.quantum.qsharp.operationsandfunctions)的主体，然后在直接或通过其他操作---调用时运行。</span><span class="sxs-lookup"><span data-stu-id="227c9-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.qsharp.operationsandfunctions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="227c9-121">因此，您可以编写以下形式的操作：</span><span class="sxs-lookup"><span data-stu-id="227c9-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="227c9-122">您定义了一个操作， `MeasureSuperposition` 该操作不使用输入并返回类型 [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types)的值。</span><span class="sxs-lookup"><span data-stu-id="227c9-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span></span>

<span data-ttu-id="227c9-123">除了操作外， Q# 还允许将确定性计算封装到函数中。</span><span class="sxs-lookup"><span data-stu-id="227c9-123">In addition to operations, Q# also allows to encapsulate deterministic computations into functions.</span></span> <span data-ttu-id="227c9-124">除了确定性保证以外，qubits 的计算需要封装到操作而不是函数中，操作和函数之间的差异很小。</span><span class="sxs-lookup"><span data-stu-id="227c9-124">Aside from the determinism guarantee that implies that computations that act on qubits need to be encapsulated into operations rather than functions, there is little difference between operations and function.</span></span> <span data-ttu-id="227c9-125">我们将它们统称为 *callables*。</span><span class="sxs-lookup"><span data-stu-id="227c9-125">We refer to them collectively as *callables*.</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="227c9-126">在文件中定义的可调用 Q#</span><span class="sxs-lookup"><span data-stu-id="227c9-126">Callable defined in a Q# file</span></span>

<span data-ttu-id="227c9-127">可调用只是由调用和运行的 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-127">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="227c9-128">但是，它需要额外添加一些内容才能包含完整 `*.qs` Q# 文件。</span><span class="sxs-lookup"><span data-stu-id="227c9-128">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="227c9-129">所有 Q# 类型和 callables 都 (您定义的类型和) 在命名空间中定义的，这些都是在命名空间中定义的，这些 *命名空间* 提供了可引用的全名。</span><span class="sxs-lookup"><span data-stu-id="227c9-129">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="227c9-130">例如，在 [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) 和命名空间中找到和操作 [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) ， [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) ([ Q# 标准库](xref:microsoft.quantum.libraries.standard.intro)) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="227c9-130">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.libraries.standard.intro)).</span></span>
<span data-ttu-id="227c9-131">因此，它们始终可以通过其 *完整* 名称调用， `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 但始终执行此操作会导致代码非常杂乱。</span><span class="sxs-lookup"><span data-stu-id="227c9-131">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="227c9-132">相反， `open` 语句允许用更简洁的速记来引用 callables，正如以上操作体中所做的那样。</span><span class="sxs-lookup"><span data-stu-id="227c9-132">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="227c9-133">Q#因此，包含我们的操作的完整文件将由定义自己的命名空间，为操作使用的 callables 打开命名空间，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="227c9-133">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="227c9-134">命名空间也可以在打开时为 *别名* ，这在两个命名空间中的可调用/类型名称冲突时非常有用。</span><span class="sxs-lookup"><span data-stu-id="227c9-134">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="227c9-135">例如，我们可以使用 `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` 上面的，然后 `H` 通过调用 `NamespaceWithH.H(<qubit>)` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-135">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="227c9-136">所有这些都是一个例外，即 [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) 始终自动打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="227c9-136">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="227c9-137">因此， [`Length`](xref:Microsoft.Quantum.Core.Length) 可以始终直接使用 callables 等。</span><span class="sxs-lookup"><span data-stu-id="227c9-137">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="227c9-138">在目标计算机上运行</span><span class="sxs-lookup"><span data-stu-id="227c9-138">Running on target machines</span></span>

<span data-ttu-id="227c9-139">现在，程序的常规运行模型 Q# 变得清晰。</span><span class="sxs-lookup"><span data-stu-id="227c9-139">Now the general run model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="227c9-140">首先，要运行的特定调用有权访问在同一命名空间中定义的任何其他 callables 和类型。</span><span class="sxs-lookup"><span data-stu-id="227c9-140">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="227c9-141">它还从任何库访问这些库，但必须通过其全名或使用上述语句来引用这些[ Q# 库](xref:microsoft.quantum.libraries) `open` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-141">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="227c9-142">然后在 *[目标计算机](xref:microsoft.quantum.machines)* 上运行可调用本身。</span><span class="sxs-lookup"><span data-stu-id="227c9-142">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="227c9-143">此类目标计算机可以是实际的量程硬件，也可以是多个模拟器作为 QDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="227c9-143">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="227c9-144">对于我们的目的，最有用的目标计算机是 [全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)的实例， `QuantumSimulator` 它计算程序的行为，就好像它是在无噪音的量程计算机上运行一样。</span><span class="sxs-lookup"><span data-stu-id="227c9-144">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="227c9-145">到目前为止，我们已介绍了在运行特定的 Q# 可调用时将发生的情况。</span><span class="sxs-lookup"><span data-stu-id="227c9-145">So far, we've described what happens when a specific Q# callable is being run.</span></span>
<span data-ttu-id="227c9-146">无论 Q# 是在独立应用程序还是主机程序中使用，此常规过程都---相同的，因此 QDK 的灵活性。</span><span class="sxs-lookup"><span data-stu-id="227c9-146">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="227c9-147">因此，调用量子开发工具包的方法之间的区别在于，它会在调用可 *调用的方式* Q# 和返回任何结果的方式之间展现出来。</span><span class="sxs-lookup"><span data-stu-id="227c9-147">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="227c9-148">更具体地说，区别在于：</span><span class="sxs-lookup"><span data-stu-id="227c9-148">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="227c9-149">指示 Q# 要运行的调用的</span><span class="sxs-lookup"><span data-stu-id="227c9-149">Indicating which Q# callable is to be run</span></span>
- <span data-ttu-id="227c9-150">如何提供可能的可调用参数</span><span class="sxs-lookup"><span data-stu-id="227c9-150">How potential callable arguments are provided</span></span>
- <span data-ttu-id="227c9-151">指定在其上运行它的目标计算机</span><span class="sxs-lookup"><span data-stu-id="227c9-151">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="227c9-152">返回结果的方式</span><span class="sxs-lookup"><span data-stu-id="227c9-152">How any results are returned</span></span>

<span data-ttu-id="227c9-153">首先，我们将讨论如何在 Q# 命令提示符下使用独立的应用程序完成此操作，然后继续使用 Python 和 c # 宿主程序。</span><span class="sxs-lookup"><span data-stu-id="227c9-153">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="227c9-154">我们保留了 Jupyter 笔记本的独立应用程序 Q# ，因为它与前三个不同，主要功能并不围绕本地 Q# 文件。</span><span class="sxs-lookup"><span data-stu-id="227c9-154">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="227c9-155">虽然我们在这些示例中并不说明这种情况，但在运行方法中，从程序内部打印的任何消息都 Q# (通过或进行的 [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ，例如) 通常会始终打印到各自的控制台。</span><span class="sxs-lookup"><span data-stu-id="227c9-155">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="227c9-156">Q# 从命令提示符</span><span class="sxs-lookup"><span data-stu-id="227c9-156">Q# from the command prompt</span></span>
<span data-ttu-id="227c9-157">开始编写程序的最简单方法之一 Q# 是避免担心单独的文件和另一种语言。</span><span class="sxs-lookup"><span data-stu-id="227c9-157">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="227c9-158">通过使用 Visual Studio Code 或带有 QDK 扩展的 Visual Studio，可以实现一个无缝的工作流，其中 Q# 仅从一个文件中运行 callables Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-158">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="227c9-159">为此，我们将通过输入</span><span class="sxs-lookup"><span data-stu-id="227c9-159">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="227c9-160">。</span><span class="sxs-lookup"><span data-stu-id="227c9-160">at the command prompt.</span></span>
<span data-ttu-id="227c9-161">最简单的工作流是：终端的目录位置与 Q# 文件相同，例如，可以 Q# 使用 VS Code 中的集成终端轻松地与文件编辑进行处理。</span><span class="sxs-lookup"><span data-stu-id="227c9-161">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="227c9-162">但是，该[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)接受多个选项，也可以通过仅提供文件的位置，在其他位置运行该程序 `--project <PATH>` Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-162">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="227c9-163">向文件添加入口点 Q#</span><span class="sxs-lookup"><span data-stu-id="227c9-163">Add entry point to Q# file</span></span>

<span data-ttu-id="227c9-164">大多数 Q# 文件将包含多个可调用的，因此，我们当然需要让编译器知道在提供命令时要运行 *的* 调用 `dotnet run` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-164">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="227c9-165">这是通过简单更改文件本身来完成的 Q# ：</span><span class="sxs-lookup"><span data-stu-id="227c9-165">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="227c9-166">`@EntryPoint()`在可调用的前面添加一行。</span><span class="sxs-lookup"><span data-stu-id="227c9-166">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="227c9-167">这样，我们的文件就会成为</span><span class="sxs-lookup"><span data-stu-id="227c9-167">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="227c9-168">现在， `dotnet run` 从命令提示符调用 `MeasureSuperposition` 会导致运行，然后将返回值直接打印到终端。</span><span class="sxs-lookup"><span data-stu-id="227c9-168">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="227c9-169">因此，您将看到 `One` 或已 `Zero` 打印。</span><span class="sxs-lookup"><span data-stu-id="227c9-169">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="227c9-170">请注意，如果下面定义了更多的 callables，则将只 `MeasureSuperposition` 运行。</span><span class="sxs-lookup"><span data-stu-id="227c9-170">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="227c9-171">此外，如果您的可调用内容在其声明之前包含 [文档注释](xref:microsoft.quantum.qsharp.comments#documentation-comments) ，则不会出现问题 `@EntryPoint()` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-171">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="227c9-172">可调用参数</span><span class="sxs-lookup"><span data-stu-id="227c9-172">Callable arguments</span></span>

<span data-ttu-id="227c9-173">到目前为止，我们只被视为不需要输入的操作。</span><span class="sxs-lookup"><span data-stu-id="227c9-173">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="227c9-174">假设我们想要执行类似的操作，但在多个 qubits 上---作为参数提供的数量。</span><span class="sxs-lookup"><span data-stu-id="227c9-174">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="227c9-175">此类操作可以编写为</span><span class="sxs-lookup"><span data-stu-id="227c9-175">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="227c9-176">其中，返回值是度量结果的数组。</span><span class="sxs-lookup"><span data-stu-id="227c9-176">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="227c9-177">请注意， [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) 和 [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) 位于 [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) 和 [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 命名空间中，每个都需要其他 `open` 语句。</span><span class="sxs-lookup"><span data-stu-id="227c9-177">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="227c9-178">如果将属性移 `@EntryPoint()` 到此新操作之前 (请注意，在文件中只能有一个这样的行) ，尝试运行它只会 `dotnet run` 导致错误消息，指出需要其他哪些命令行选项以及如何表达它们。</span><span class="sxs-lookup"><span data-stu-id="227c9-178">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="227c9-179">命令行的常规格式实际上是 `dotnet run [options]` ，并在此处提供了可调用的参数。</span><span class="sxs-lookup"><span data-stu-id="227c9-179">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="227c9-180">在这种情况下， `n` 缺少参数，并显示需要提供选项 `-n <n>` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-180">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="227c9-181">若要 `MeasureSuperpositionArray` 运行 `n=4` qubits，我们将使用</span><span class="sxs-lookup"><span data-stu-id="227c9-181">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="227c9-182">生成类似于的输出</span><span class="sxs-lookup"><span data-stu-id="227c9-182">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="227c9-183">当然，这种情况下会扩展到多个参数。</span><span class="sxs-lookup"><span data-stu-id="227c9-183">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="227c9-184">在中定义的参数名称在编译器中进行 `camelCase` 了轻微更改，作为 Q# 输入接受。</span><span class="sxs-lookup"><span data-stu-id="227c9-184">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="227c9-185">例如，如果 `n` 使用上面的名称， `numQubits` 则此输入将通过 `--num-qubits 4` 而不是在命令行中提供 `-n 4` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-185">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="227c9-186">错误消息还提供可供使用的其他选项，包括如何更改目标计算机。</span><span class="sxs-lookup"><span data-stu-id="227c9-186">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="227c9-187">不同的目标计算机</span><span class="sxs-lookup"><span data-stu-id="227c9-187">Different target machines</span></span>

<span data-ttu-id="227c9-188">由于我们的操作的输出在实际 qubits 上是其操作的预期结果，因此，从命令行到默认的目标计算机是完全状态的量程模拟器 `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-188">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="227c9-189">但是，我们可以指示 callables 在特定目标计算机上运行， `--simulator` (或简写 `-s`) 。</span><span class="sxs-lookup"><span data-stu-id="227c9-189">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="227c9-190">例如，可以在上运行它 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ：</span><span class="sxs-lookup"><span data-stu-id="227c9-190">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="227c9-191">然后，打印输出</span><span class="sxs-lookup"><span data-stu-id="227c9-191">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="227c9-192">有关这些指标的含义的详细信息，请参阅 [Resource 估计器：报告的度量值](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)。</span><span class="sxs-lookup"><span data-stu-id="227c9-192">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="227c9-193">命令行运行摘要</span><span class="sxs-lookup"><span data-stu-id="227c9-193">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="227c9-194">非 Q# `dotnet run` 选项</span><span class="sxs-lookup"><span data-stu-id="227c9-194">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="227c9-195">如上所述 `--project` ，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)还接受与可调用参数无关的选项 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-195">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="227c9-196">如果同时提供这两种选项，则 `dotnet` 必须先提供特定于的选项，然后再提供分隔符 `--` ，然后 Q# 选择特定的选项。</span><span class="sxs-lookup"><span data-stu-id="227c9-196">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="227c9-197">例如，为上述操作指定路径和数字 qubits 将通过运行 `dotnet run --project <PATH> -- -n <n>` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-197">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="227c9-198">Q# 具有主机程序</span><span class="sxs-lookup"><span data-stu-id="227c9-198">Q# with host programs</span></span>

<span data-ttu-id="227c9-199">使用我们的 Q# 文件，从命令提示符直接调用操作或函数的替代方法是使用另一种传统语言的 *主机程序* 。</span><span class="sxs-lookup"><span data-stu-id="227c9-199">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="227c9-200">具体而言，可以使用 Python 或 .NET 语言（如 c # 或 F # (）实现此目的。为了简单起见，我们只会在此处) 详细说明 c #。</span><span class="sxs-lookup"><span data-stu-id="227c9-200">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="227c9-201">若要启用互操作性，还需要进行一些设置，但这些详细信息可在 [安装指南](xref:microsoft.quantum.install)中找到。</span><span class="sxs-lookup"><span data-stu-id="227c9-201">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="227c9-202">简而言之，这种情况下， (例如， `*.py` 或 `*.cs` 在文件所在的同一位置) Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-202">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="227c9-203">它现在是运行的 *主机* 程序，在运行时，它可以 Q# 从文件调用特定的操作和函数 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-203">It's now the *host* program that gets run, and while it is running, it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="227c9-204">互操作性的核心基于 Q# 编译器使文件内容可供 Q# 主机程序访问，以便可以调用。</span><span class="sxs-lookup"><span data-stu-id="227c9-204">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="227c9-205">使用主机程序的一个主要优点是， Q# 可以使用主机语言进一步处理程序返回的传统数据。</span><span class="sxs-lookup"><span data-stu-id="227c9-205">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="227c9-206">这可能包括一些高级的数据处理 (例如，不能在内部) 内执行的内容， Q# 然后 Q# 基于这些结果调用进一步的操作，或者像绘制结果那样简单 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-206">This could consist of some advanced data processing (for example, something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="227c9-207">此处显示了一般方案，并讨论了下面的 Python 和 c # 的具体实现。</span><span class="sxs-lookup"><span data-stu-id="227c9-207">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="227c9-208">有关使用 F # 宿主程序的示例，请参阅 [.net 互操作性示例](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)。</span><span class="sxs-lookup"><span data-stu-id="227c9-208">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="227c9-209">用于 `@EntryPoint()` Q# 应用程序的属性不能与主机程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="227c9-209">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="227c9-210">如果主机正在调用的文件中存在错误，则会引发错误 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-210">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="227c9-211">若要使用不同的主机程序，不需要对文件进行任何更改 `*.qs` Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-211">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="227c9-212">以下主机程序实现均使用相同的 Q# 文件：</span><span class="sxs-lookup"><span data-stu-id="227c9-212">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="227c9-213">选择与您感兴趣的主机语言对应的选项卡。</span><span class="sxs-lookup"><span data-stu-id="227c9-213">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="227c9-214">Python</span><span class="sxs-lookup"><span data-stu-id="227c9-214">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="227c9-215">Python 主机计划如下所示：</span><span class="sxs-lookup"><span data-stu-id="227c9-215">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="227c9-216">导入 `qsharp` 模块，该模块将注册模块加载程序以实现 Q# 互操作性。</span><span class="sxs-lookup"><span data-stu-id="227c9-216">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="227c9-217">这允许 Q# 命名空间显示为 Python 模块，我们可以将其 "导入" callables "导入" Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-217">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="227c9-218">请注意，从技术上讲，它并不是 Q# 导入的 callables 本身，而是允许调用它们的 Python 存根。</span><span class="sxs-lookup"><span data-stu-id="227c9-218">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="227c9-219">它们表现为 Python 类的对象。</span><span class="sxs-lookup"><span data-stu-id="227c9-219">These behave as objects of Python classes.</span></span> <span data-ttu-id="227c9-220">我们使用这些对象的方法来指定在运行程序时将操作发送到的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="227c9-220">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="227c9-221">导入这些 Q# callables，我们将在此示例中直接调用--- `MeasureSuperposition` 和 `MeasureSuperpositionArray` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-221">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="227c9-222">`qsharp`导入模块后，还可以直接从 Q# 库命名空间导入 callables。</span><span class="sxs-lookup"><span data-stu-id="227c9-222">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="227c9-223">在其他任何 Python 代码中，现在可以在特定目标计算机上调用这些 callables，并将其返回值分配给变量 (如果它们返回值) 以便进一步使用。</span><span class="sxs-lookup"><span data-stu-id="227c9-223">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="227c9-224">指定目标计算机</span><span class="sxs-lookup"><span data-stu-id="227c9-224">Specifying target machines</span></span>
<span data-ttu-id="227c9-225">调用要在特定目标计算机上运行的操作是通过导入的对象上的不同 Python 方法完成的。</span><span class="sxs-lookup"><span data-stu-id="227c9-225">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="227c9-226">例如， `.simulate(<args>)` 使用 `QuantumSimulator` 运行操作，而 `.estimate_resources(<args>)` 在上执行此操作 `ResourcesEstimator` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-226">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="227c9-227">向 Q 传递输入\#</span><span class="sxs-lookup"><span data-stu-id="227c9-227">Passing inputs to Q\#</span></span>
<span data-ttu-id="227c9-228">Q#应以关键字参数的形式提供可调用的参数，其中，关键字是可调用定义中的参数名称 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-228">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="227c9-229">这是 `MeasureSuperpositionArray.simulate(n=4)` 有效的，但 `MeasureSuperpositionArray.simulate(4)` 会引发错误。</span><span class="sxs-lookup"><span data-stu-id="227c9-229">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="227c9-230">因此，Python 主机程序</span><span class="sxs-lookup"><span data-stu-id="227c9-230">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="227c9-231">生成如下所示的输出：</span><span class="sxs-lookup"><span data-stu-id="227c9-231">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="227c9-232">使用 Q# 其他项目或包中的代码</span><span class="sxs-lookup"><span data-stu-id="227c9-232">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="227c9-233">默认情况下，该 `import qsharp` 命令 `.qs` 会加载当前文件夹中的所有文件，并使其 Q# 操作和函数可供在 Python 脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="227c9-233">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="227c9-234">若要 Q# 从其他文件夹加载代码，可以使用[ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects)来添加对项目的引用 `.csproj` Q# (即引用) 的项目 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-234">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="227c9-235">此命令将编译 `.qs` 包含及其子文件夹的文件夹中的任何文件 `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-235">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="227c9-236">它还会以递归方式加载通过 `PackageReference` 或 Q# 通过该文件引用的项目引用的任何包 `ProjectReference` `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-236">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="227c9-237">例如，以下 Python 代码将导入外部项目，并引用其相对于当前文件夹的路径，并调用其 Q# 操作之一：</span><span class="sxs-lookup"><span data-stu-id="227c9-237">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="227c9-238">这会生成类似于以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="227c9-238">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="227c9-239">若要加载包含代码的外部包 Q# ，请使用[ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)。</span><span class="sxs-lookup"><span data-stu-id="227c9-239">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="227c9-240">如果 Q# 当前文件夹中的代码依赖于外部项目或包，则在运行时可能会看到错误 `import qsharp` ，因为尚未加载依赖关系。</span><span class="sxs-lookup"><span data-stu-id="227c9-240">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="227c9-241">若要在命令期间加载所需的外部包或 Q# 项目 `import qsharp` ，请确保具有 Python 脚本的文件夹包含 `.csproj` 引用的文件 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-241">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="227c9-242">在这种情况 `.csproj` 下，将属性添加 `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` 到中 `<PropertyGroup>` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-242">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="227c9-243">这将指示我在 Q# 命令过程中以递归方式加载 `ProjectReference` `PackageReference` 在中找到的任何或项 `.csproj` `import qsharp` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-243">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="227c9-244">例如，下面是一个简单的 `.csproj` 文件，该文件将导致 Q# 自动加载 `Microsoft.Quantum.Chemistry` 包：</span><span class="sxs-lookup"><span data-stu-id="227c9-244">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="227c9-245">目前， `<IQSharpLoadAutomatically>` python 主机需要此自定义属性，但在将来，这可能会成为与 `.csproj` Python 脚本位于同一文件夹中的文件的默认行为。</span><span class="sxs-lookup"><span data-stu-id="227c9-245">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="227c9-246">目前， `<QsharpCompile>` `.csproj` Python 主机会忽略中的设置，并且 `.qs` 加载并编译 (的文件夹中的所有文件 `.csproj` （包括子文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="227c9-246">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="227c9-247">`.csproj`以后将改进对设置的支持 (参阅[iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277)了解更多详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="227c9-247">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="227c9-248">C#</span><span class="sxs-lookup"><span data-stu-id="227c9-248">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="227c9-249">C # 主机程序具有多个组件，并与 QDK 的某些组件（如模拟器）非常紧密，这些组件是在 c # 的基础上构建的。</span><span class="sxs-lookup"><span data-stu-id="227c9-249">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="227c9-250">Q#编译器在此处通过 Q# 在文件的命名空间中生成一个等效的 c # 命名空间来工作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-250">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="227c9-251">它针对其中定义的每个 callables 或类型进一步生成一个等效的命名 c # 类 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-251">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="227c9-252">首先，我们将在主机程序中使用的类与语句一起使用 `using` ，这些语句大致类似于 `open` 文件中的语句 Q# ：</span><span class="sxs-lookup"><span data-stu-id="227c9-252">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="227c9-253">接下来，我们声明 c # 命名空间，一些其他位和部分 (查看以下完整的代码块) ，然后使用任何传统编程 (例如，计算 Q# callables) 的参数。</span><span class="sxs-lookup"><span data-stu-id="227c9-253">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the Q# callables).</span></span>
<span data-ttu-id="227c9-254">在本例中，后者不是必需的，但在  [.net 互操作性示例](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)中可以找到此类用法的示例。</span><span class="sxs-lookup"><span data-stu-id="227c9-254">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="227c9-255">目标计算机</span><span class="sxs-lookup"><span data-stu-id="227c9-255">Target machines</span></span>

<span data-ttu-id="227c9-256">返回到 Q# ，必须创建将在其上运行操作的任何目标计算机的实例。</span><span class="sxs-lookup"><span data-stu-id="227c9-256">Getting back to Q#, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="227c9-257">使用其他目标计算机非常简单，只需要实例化不同的计算机，但执行此操作和处理返回的方式可能略有不同。</span><span class="sxs-lookup"><span data-stu-id="227c9-257">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="227c9-258">为简洁起见，我们现在坚持到 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ，并包括 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [以下](#including-the-resources-estimator)。</span><span class="sxs-lookup"><span data-stu-id="227c9-258">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="227c9-259">每个从操作生成的 c # 类 Q# 都有一个 `Run` 方法，第一个参数必须是目标计算机实例。</span><span class="sxs-lookup"><span data-stu-id="227c9-259">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="227c9-260">因此，若要 `MeasureSuperposition` 在上运行 `QuantumSimulator` ，我们将使用 `MeasureSuperposition.Run(sim)` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-260">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="227c9-261">然后，可以将返回的结果分配给 c # 中的变量：</span><span class="sxs-lookup"><span data-stu-id="227c9-261">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="227c9-262">`Run`方法以异步方式运行，因为这将是真实量程硬件的情况，因此， `await` 关键字会阻止进一步的处理，直到任务完成。</span><span class="sxs-lookup"><span data-stu-id="227c9-262">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="227c9-263">如果可 Q# 调用的不包含任何返回 (例如，它具有返回类型 `Unit`) ，则仍可通过相同的方式执行运行，而无需将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="227c9-263">If the Q# callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="227c9-264">在这种情况下，整行只包含</span><span class="sxs-lookup"><span data-stu-id="227c9-264">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="227c9-265">参数</span><span class="sxs-lookup"><span data-stu-id="227c9-265">Arguments</span></span>

<span data-ttu-id="227c9-266">可调用的任何参数在 Q# 目标计算机之后都作为附加自变量传递。</span><span class="sxs-lookup"><span data-stu-id="227c9-266">Any arguments to the Q# callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="227c9-267">因此， `MeasureSuperpositionArray` qubits 上的结果 `n=4` 将通过</span><span class="sxs-lookup"><span data-stu-id="227c9-267">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="227c9-268">因此，完整的 c # 宿主程序可能类似于</span><span class="sxs-lookup"><span data-stu-id="227c9-268">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="227c9-269">在 c # 文件的位置，通过输入，可以从命令提示符运行主机程序</span><span class="sxs-lookup"><span data-stu-id="227c9-269">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="227c9-270">在这种情况下，你将看到写入到控制台的输出，类似于</span><span class="sxs-lookup"><span data-stu-id="227c9-270">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="227c9-271">由于编译器与命名空间的互操作性，因此，我们可以 Q# 在不使用语句的情况下让 callables 可用 `using NamespaceName;` ，并且只需将 c # 命名空间标题与它进行匹配即可。</span><span class="sxs-lookup"><span data-stu-id="227c9-271">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="227c9-272">也就是说，将替换 `namespace host` 为 `namespace NamespaceName` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-272">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="227c9-273">包括资源估计器</span><span class="sxs-lookup"><span data-stu-id="227c9-273">Including the resources estimator</span></span>

<span data-ttu-id="227c9-274">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)需要略有不同的实现来检索输出。</span><span class="sxs-lookup"><span data-stu-id="227c9-274">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="227c9-275">首先，不会将它们实例化为带有语句的变量 `using` (与 `QuantumSimulator`) 一样，我们通过</span><span class="sxs-lookup"><span data-stu-id="227c9-275">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="227c9-276">请注意， Q# 我们已为每个操作实例化一个目标模拟器，而不是由多个操作使用单个目标模拟器。</span><span class="sxs-lookup"><span data-stu-id="227c9-276">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="227c9-277">这是因为在用作目标计算机时，对象本身会被修改，然后可以使用类方法在以后检索这些对象的结果 `.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-277">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="227c9-278">若要在资源估算上运行操作，请使用</span><span class="sxs-lookup"><span data-stu-id="227c9-278">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="227c9-279">然后，将结果作为制表符分隔的值（ (TSV) 与和一起提取 `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-279">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="227c9-280">因此，使用和的完整 c # 宿主程序 `QuantumSimulator` `ResourcesEstimator` 可以采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="227c9-280">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="227c9-281">这会生成类似于的输出</span><span class="sxs-lookup"><span data-stu-id="227c9-281">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="227c9-282">Q# Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="227c9-282">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="227c9-283">Q# Jupyter 笔记本利用 I Q# 内核，使你能够在单个笔记本中定义、编译和运行 Q# callables，---所有说明、注释和其他内容。</span><span class="sxs-lookup"><span data-stu-id="227c9-283">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="227c9-284">这意味着，虽然可以导入和使用文件的内容，但 `*.qs` Q# 它们在运行模型中并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="227c9-284">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the run model.</span></span>

<span data-ttu-id="227c9-285">在这里，我们将详细介绍如何运行 Q# 上面定义的操作，但 Q# 在 [简介 Q# 和 Jupyter 笔记本](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)中提供了有关使用 Jupyter 笔记本的更广泛的介绍。</span><span class="sxs-lookup"><span data-stu-id="227c9-285">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="227c9-286">定义操作</span><span class="sxs-lookup"><span data-stu-id="227c9-286">Defining operations</span></span>

<span data-ttu-id="227c9-287">在 Q# Jupyter Notebook 中，你可以 Q# 像在文件的命名空间内一样输入代码 Q# 。</span><span class="sxs-lookup"><span data-stu-id="227c9-287">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="227c9-288">因此，可以从具有相应命名空间的语句的[ Q# 标准库](xref:microsoft.quantum.libraries.standard.intro)中启用对 callables 的访问 `open` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-288">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="227c9-289">使用此类语句运行单元时，这些命名空间中的定义在整个工作区中都可用。</span><span class="sxs-lookup"><span data-stu-id="227c9-289">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="227c9-290">Callables 和[Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) [Canon](xref:Microsoft.Quantum.Canon) (例如， [`H`](xref:Microsoft.Quantum.Intrinsic.H) 和 [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) 自动可用于 Q# Jupyter 笔记本的单元内定义的操作中。</span><span class="sxs-lookup"><span data-stu-id="227c9-290">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="227c9-291">不过，对于从外部源文件引入的代码)  (，这种情况并不是如此 Q# 。 [ Q# ](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="227c9-291">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="227c9-292">同样，定义操作只需编写 Q# 代码并运行单元。</span><span class="sxs-lookup"><span data-stu-id="227c9-292">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="227c9-293">然后，输出会列出这些操作，随后可以从未来的单元格中调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="227c9-293">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="227c9-294">目标计算机</span><span class="sxs-lookup"><span data-stu-id="227c9-294">Target machines</span></span>

<span data-ttu-id="227c9-295">通过 [I Q# 幻命令](xref:microsoft.quantum.guide.quickref.iqsharp)提供在特定目标计算机上运行操作的功能。</span><span class="sxs-lookup"><span data-stu-id="227c9-295">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="227c9-296">例如， `%simulate` 利用 `QuantumSimulator` ，并 `%estimate` 使用 `ResourcesEstimator` ：</span><span class="sxs-lookup"><span data-stu-id="227c9-296">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="227c9-297">将输入传递到函数和操作</span><span class="sxs-lookup"><span data-stu-id="227c9-297">Passing inputs to functions and operations</span></span>

<span data-ttu-id="227c9-298">若要将输入传递到 Q# 操作，可以将参数传递为 `key=value` "运行魔术" 命令。</span><span class="sxs-lookup"><span data-stu-id="227c9-298">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="227c9-299">因此，若要运行 `MeasureSuperpositionArray` 四个 qubits，可以运行 `%simulate MeasureSuperpositionArray n=4` ：</span><span class="sxs-lookup"><span data-stu-id="227c9-299">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="227c9-300">此模式可与 `%estimate` 和其他运行命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="227c9-300">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="227c9-301">使用 Q# 其他项目或包中的代码</span><span class="sxs-lookup"><span data-stu-id="227c9-301">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="227c9-302">默认情况下， Q# Jupyter Notebook 加载 `.qs` 当前文件夹中的所有文件，并使其 Q# 操作和函数可从笔记本内部使用。</span><span class="sxs-lookup"><span data-stu-id="227c9-302">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="227c9-303">[ `%who` 魔术命令](xref:microsoft.quantum.iqsharp.magic-ref.who)列出了当前可用的所有 Q# 操作和函数。</span><span class="sxs-lookup"><span data-stu-id="227c9-303">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="227c9-304">若要 Q# 从另一个文件夹加载代码，可以使用[ `%project` 魔棒命令](xref:microsoft.quantum.iqsharp.magic-ref.project)为项目添加对 `.csproj` 文件的引用 Q# (即引用) 的项目 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-304">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="227c9-305">此命令将编译 `.qs` 包含 `.csproj`) 的 (和子文件夹的文件夹中的任何文件。</span><span class="sxs-lookup"><span data-stu-id="227c9-305">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="227c9-306">它还会以递归方式加载通过 `PackageReference` 或 Q# 通过该文件引用的项目引用的任何包 `ProjectReference` `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-306">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="227c9-307">例如，下面的单元模拟了 Q# 外部项目中的操作，该项目路径相对于当前文件夹引用：</span><span class="sxs-lookup"><span data-stu-id="227c9-307">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="227c9-308">若要加载包含 Q# 代码的外部包，请使用[ `%package` 魔棒命令](xref:microsoft.quantum.iqsharp.magic-ref.package)。</span><span class="sxs-lookup"><span data-stu-id="227c9-308">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="227c9-309">加载包还会使任何自定义的幻命令或显示包含在包中的任何程序集中的编码器。</span><span class="sxs-lookup"><span data-stu-id="227c9-309">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="227c9-310">若要 Q# 在笔记本初始化时加载外部包或项目，请确保笔记本文件夹包含 `.csproj` 引用的文件 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-310">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="227c9-311">在这种情况 `.csproj` 下，将属性添加 `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` 到中 `<PropertyGroup>` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-311">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="227c9-312">这将指示我 Q# 以递归方式加载 `ProjectReference` `PackageReference` 在笔记本加载时在中找到的任何或项 `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="227c9-312">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="227c9-313">例如，下面是一个简单的 `.csproj` 文件，该文件将导致 Q# 自动加载 `Microsoft.Quantum.Chemistry` 包：</span><span class="sxs-lookup"><span data-stu-id="227c9-313">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="227c9-314">目前 `<IQSharpLoadAutomatically>` Jupyter Notebook 主机需要此自定义属性 Q# ，但在将来，这可能会成为与 `.csproj` 笔记本文件位于同一文件夹中的文件的默认行为。</span><span class="sxs-lookup"><span data-stu-id="227c9-314">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="227c9-315">目前 `<QsharpCompile>` `.csproj` Jupyter Notebook 主机忽略中的设置 Q# ，并且 `.qs` 加载和编译 (的文件夹中的所有文件 `.csproj` （包括子) 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="227c9-315">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="227c9-316">`.csproj`以后将改进对设置的支持 (参阅[iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277)了解更多详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="227c9-316">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
