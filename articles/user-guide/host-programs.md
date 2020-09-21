---
title: 运行程序的方式 Q#
description: 运行程序的不同方法的概述 Q# 。 Q#在 Python 或 .net 语言的命令提示符下，Jupyter 笔记本和经典主机程序。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: f24c608ffc6522cb50f512de1a02b3db4b290e83
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759810"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="b414a-104">运行程序的方式 Q#</span><span class="sxs-lookup"><span data-stu-id="b414a-104">Ways to run a Q# program</span></span>

<span data-ttu-id="b414a-105">量程开发工具包的最大优势之一是其跨平台和开发环境的灵活性。</span><span class="sxs-lookup"><span data-stu-id="b414a-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="b414a-106">但是，这也意味着，新 Q# 用户可能会发现，在 [安装指南](xref:microsoft.quantum.install)中找到的众多选项可能会混淆或淹没。</span><span class="sxs-lookup"><span data-stu-id="b414a-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="b414a-107">在此页上，我们将介绍运行程序时所发生的情况 Q# ，并比较用户可执行此操作的不同方式。</span><span class="sxs-lookup"><span data-stu-id="b414a-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="b414a-108">主要区别在于， Q# 可以运行：</span><span class="sxs-lookup"><span data-stu-id="b414a-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="b414a-109">作为独立的应用程序，其中 Q# 是所涉及的唯一语言，直接调用程序。</span><span class="sxs-lookup"><span data-stu-id="b414a-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="b414a-110">这两种方法实际上属于此类别：</span><span class="sxs-lookup"><span data-stu-id="b414a-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="b414a-111">命令行接口</span><span class="sxs-lookup"><span data-stu-id="b414a-111">the command-line interface</span></span>
  - <span data-ttu-id="b414a-112">Q# Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="b414a-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="b414a-113">使用以 Python 或 .NET 语言编写的其他 *主机程序* (例如 c # 或 F # ) ，然后调用程序并可以进一步处理返回的结果。</span><span class="sxs-lookup"><span data-stu-id="b414a-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="b414a-114">为了更好地了解这些过程及其区别，我们考虑了一个简单 Q# 的程序并对其执行方式进行比较。</span><span class="sxs-lookup"><span data-stu-id="b414a-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="b414a-115">基本 Q# 计划</span><span class="sxs-lookup"><span data-stu-id="b414a-115">Basic Q# program</span></span>

<span data-ttu-id="b414a-116">基本的量程计划可能包含：在状态 $ \ket {0} $ 和 $ \ket $ 的 superposition 中准备 qubit {1} ，对其进行度量，并返回结果，这两种状态将随机成为具有相同概率的两种状态之一。</span><span class="sxs-lookup"><span data-stu-id="b414a-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="b414a-117">事实上，此过程是 [量程随机数生成器](xref:microsoft.quantum.quickstarts.qrng) 快速入门的核心。</span><span class="sxs-lookup"><span data-stu-id="b414a-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="b414a-118">在中 Q# ，这将由以下代码执行：</span><span class="sxs-lookup"><span data-stu-id="b414a-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="b414a-119">但是，此代码本身不能由执行 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="b414a-120">为此，它需要构成操作的主体，然后在直接或通过其他操作---调用时执行该 [操作](xref:microsoft.quantum.guide.basics#q-operations-and-functions)。</span><span class="sxs-lookup"><span data-stu-id="b414a-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="b414a-121">因此，您可以编写以下形式的操作：</span><span class="sxs-lookup"><span data-stu-id="b414a-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="b414a-122">您定义了一个操作， `MeasureSuperposition` 该操作不使用输入并返回类型 [Result](xref:microsoft.quantum.guide.types)的值。</span><span class="sxs-lookup"><span data-stu-id="b414a-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="b414a-123">虽然此页上的示例只包含 Q# *操作*，但我们所讨论的所有概念将同样适用于 Q# *函数*，因此，我们将它们统称为 *callables*。</span><span class="sxs-lookup"><span data-stu-id="b414a-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="b414a-124">它们的差异在基础上进行了讨论[ Q# ：操作和功能](xref:microsoft.quantum.guide.basics#q-operations-and-functions)，以及有关如何定义它们的详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="b414a-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="b414a-125">在文件中定义的可调用 Q#</span><span class="sxs-lookup"><span data-stu-id="b414a-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="b414a-126">可调用只是由调用和运行的 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="b414a-127">但是，它需要额外添加一些内容才能包含完整 `*.qs` Q# 文件。</span><span class="sxs-lookup"><span data-stu-id="b414a-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="b414a-128">所有 Q# 类型和 callables 都 (您定义的类型和) 在命名空间中定义的，这些都是在命名空间中定义的，这些 *命名空间*提供了可引用的全名。</span><span class="sxs-lookup"><span data-stu-id="b414a-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="b414a-129">例如，在 [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) 和命名空间中找到和操作 [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) ， [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) ([ Q# 标准库](xref:microsoft.quantum.qsharplibintro)) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b414a-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="b414a-130">因此，它们始终可以通过其 *完整* 名称调用， `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 但始终执行此操作会导致代码非常杂乱。</span><span class="sxs-lookup"><span data-stu-id="b414a-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="b414a-131">相反， `open` 语句允许用更简洁的速记来引用 callables，正如以上操作体中所做的那样。</span><span class="sxs-lookup"><span data-stu-id="b414a-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="b414a-132">Q#因此，包含我们的操作的完整文件将由定义自己的命名空间，为操作使用的 callables 打开命名空间，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b414a-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="b414a-133">命名空间也可以在打开时为 *别名* ，这在两个命名空间中的可调用/类型名称冲突时非常有用。</span><span class="sxs-lookup"><span data-stu-id="b414a-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="b414a-134">例如，我们可以使用 `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` 上面的，然后 `H` 通过调用 `NamespaceWithH.H(<qubit>)` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="b414a-135">所有这些都是一个例外，即 [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) 始终自动打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b414a-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="b414a-136">因此， [`Length`](xref:microsoft.quantum.core.length) 可以始终直接使用 callables 等。</span><span class="sxs-lookup"><span data-stu-id="b414a-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="b414a-137">在目标计算机上执行</span><span class="sxs-lookup"><span data-stu-id="b414a-137">Execution on target machines</span></span>

<span data-ttu-id="b414a-138">现在，程序的常规执行模型 Q# 变得清晰。</span><span class="sxs-lookup"><span data-stu-id="b414a-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="b414a-139">首先，要执行的特定可调用有权访问在同一命名空间中定义的任何其他 callables 和类型。</span><span class="sxs-lookup"><span data-stu-id="b414a-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="b414a-140">它还从任何库访问这些库，但必须通过其全名或使用上述语句来引用这些[ Q# 库](xref:microsoft.quantum.libraries) `open` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="b414a-141">然后在 *[目标计算机](xref:microsoft.quantum.machines)* 上执行可调用本身。</span><span class="sxs-lookup"><span data-stu-id="b414a-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="b414a-142">此类目标计算机可以是实际的量程硬件，也可以是多个模拟器作为 QDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="b414a-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="b414a-143">对于我们的目的，最有用的目标计算机是 [全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)的实例， `QuantumSimulator` 它计算程序的行为，就好像是在无噪音的量程计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="b414a-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="b414a-144">到目前为止，我们已介绍了在执行特定的可调用时将发生的情况 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="b414a-145">无论 Q# 是在独立应用程序还是主机程序中使用，此常规过程都---相同的，因此 QDK 的灵活性。</span><span class="sxs-lookup"><span data-stu-id="b414a-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="b414a-146">因此，调用量子开发工具包的不同方法之间的不同之处在于 *如何* Q# 调用可调用的，并以何种方式返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="b414a-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="b414a-147">更具体地说，区别在于</span><span class="sxs-lookup"><span data-stu-id="b414a-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="b414a-148">指示 Q# 要执行的可调用的，</span><span class="sxs-lookup"><span data-stu-id="b414a-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="b414a-149">如何提供可能的可调用参数，</span><span class="sxs-lookup"><span data-stu-id="b414a-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="b414a-150">指定要在其上执行它的目标计算机，以及</span><span class="sxs-lookup"><span data-stu-id="b414a-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="b414a-151">返回结果的方式。</span><span class="sxs-lookup"><span data-stu-id="b414a-151">how any results are returned.</span></span>

<span data-ttu-id="b414a-152">首先，我们将讨论如何在 Q# 命令提示符下使用独立的应用程序完成此操作，然后继续使用 Python 和 c # 宿主程序。</span><span class="sxs-lookup"><span data-stu-id="b414a-152">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="b414a-153">我们保留了 Jupyter 笔记本的独立应用程序 Q# ，因为它与前三个不同，主要功能并不围绕本地 Q# 文件。</span><span class="sxs-lookup"><span data-stu-id="b414a-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="b414a-154">虽然我们在这些示例中并不说明这种情况，但执行方法之间的一个通用性是，从程序内部打印的任何消息都 Q# (通过 [`Message`](xref:microsoft.quantum.intrinsic.message) 或 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ，例如) 通常将始终打印到各自的控制台。</span><span class="sxs-lookup"><span data-stu-id="b414a-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="b414a-155">Q# 从命令提示符</span><span class="sxs-lookup"><span data-stu-id="b414a-155">Q# from the command prompt</span></span>
<span data-ttu-id="b414a-156">开始编写程序的最简单方法之一 Q# 是避免担心单独的文件和另一种语言。</span><span class="sxs-lookup"><span data-stu-id="b414a-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="b414a-157">通过使用 Visual Studio Code 或带有 QDK 扩展的 Visual Studio，可以实现一个无缝的工作流，其中 Q# 仅从一个文件中运行 callables Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="b414a-158">为此，我们将通过输入</span><span class="sxs-lookup"><span data-stu-id="b414a-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="b414a-159">。</span><span class="sxs-lookup"><span data-stu-id="b414a-159">at the command prompt.</span></span>
<span data-ttu-id="b414a-160">最简单的工作流是：终端的目录位置与 Q# 文件相同，例如，可以 Q# 使用 VS Code 中的集成终端轻松地与文件编辑进行处理。</span><span class="sxs-lookup"><span data-stu-id="b414a-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="b414a-161">但是，该[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)接受多个选项，也可以通过仅提供文件的位置，在其他位置运行该程序 `--project <PATH>` Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="b414a-162">向文件添加入口点 Q#</span><span class="sxs-lookup"><span data-stu-id="b414a-162">Add entry point to Q# file</span></span>

<span data-ttu-id="b414a-163">大多数 Q# 文件将包含多个可调用的，因此，我们当然需要让编译器知道在提供命令时要执行 *的可* 调用项 `dotnet run` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="b414a-164">这是通过简单更改文件本身来完成的 Q# ：</span><span class="sxs-lookup"><span data-stu-id="b414a-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="b414a-165">`@EntryPoint()`在可调用的前面添加一行。</span><span class="sxs-lookup"><span data-stu-id="b414a-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="b414a-166">这样，我们的文件就会成为</span><span class="sxs-lookup"><span data-stu-id="b414a-166">Our file from above would therefore become</span></span>
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

<span data-ttu-id="b414a-167">现在， `dotnet run` 从命令提示符调用 `MeasureSuperposition` 会导致运行，然后将返回值直接打印到终端。</span><span class="sxs-lookup"><span data-stu-id="b414a-167">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="b414a-168">因此，您将看到 `One` 或已 `Zero` 打印。</span><span class="sxs-lookup"><span data-stu-id="b414a-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="b414a-169">请注意，如果下面定义了更多的 callables，则将只 `MeasureSuperposition` 运行。</span><span class="sxs-lookup"><span data-stu-id="b414a-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="b414a-170">此外，如果您的可调用内容在其声明之前包含 [文档注释](xref:microsoft.quantum.guide.filestructure#documentation-comments) ，则不会出现问题 `@EntryPoint()` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="b414a-171">可调用参数</span><span class="sxs-lookup"><span data-stu-id="b414a-171">Callable arguments</span></span>

<span data-ttu-id="b414a-172">到目前为止，我们只被视为不需要输入的操作。</span><span class="sxs-lookup"><span data-stu-id="b414a-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="b414a-173">假设我们想要执行类似的操作，但在多个 qubits 上---作为参数提供的数量。</span><span class="sxs-lookup"><span data-stu-id="b414a-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="b414a-174">此类操作可以编写为</span><span class="sxs-lookup"><span data-stu-id="b414a-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="b414a-175">其中，返回值是度量结果的数组。</span><span class="sxs-lookup"><span data-stu-id="b414a-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="b414a-176">请注意， [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) 和 [`ForEach`](xref:microsoft.quantum.arrays.foreach) 位于 [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) 和 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 命名空间中，每个都需要其他 `open` 语句。</span><span class="sxs-lookup"><span data-stu-id="b414a-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="b414a-177">如果将属性移 `@EntryPoint()` 到此新操作之前 (请注意，在文件中只能有一个这样的行) ，尝试运行它只会 `dotnet run` 导致错误消息，指出需要其他哪些命令行选项以及如何表达它们。</span><span class="sxs-lookup"><span data-stu-id="b414a-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="b414a-178">命令行的常规格式实际上是 `dotnet run [options]` ，并在此处提供了可调用的参数。</span><span class="sxs-lookup"><span data-stu-id="b414a-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="b414a-179">在这种情况下， `n` 缺少参数，并显示需要提供选项 `-n <n>` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="b414a-180">若要 `MeasureSuperpositionArray` 运行 `n=4` qubits，我们将使用</span><span class="sxs-lookup"><span data-stu-id="b414a-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="b414a-181">生成类似于的输出</span><span class="sxs-lookup"><span data-stu-id="b414a-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="b414a-182">当然，这种情况下会扩展到多个参数。</span><span class="sxs-lookup"><span data-stu-id="b414a-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="b414a-183">在中定义的参数名称在编译器中进行 `camelCase` 了轻微更改，作为 Q# 输入接受。</span><span class="sxs-lookup"><span data-stu-id="b414a-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="b414a-184">例如，如果 `n` 使用上面的名称， `numQubits` 则此输入将通过 `--num-qubits 4` 而不是在命令行中提供 `-n 4` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="b414a-185">错误消息还提供可供使用的其他选项，包括如何更改目标计算机。</span><span class="sxs-lookup"><span data-stu-id="b414a-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="b414a-186">不同的目标计算机</span><span class="sxs-lookup"><span data-stu-id="b414a-186">Different target machines</span></span>

<span data-ttu-id="b414a-187">由于我们的操作的输出在实际 qubits 上是其操作的预期结果，因此，从命令行到默认的目标计算机是完全状态的量程模拟器 `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="b414a-188">但是，我们可以指示 callables 在特定目标计算机上运行， `--simulator` (或简写 `-s`) 。</span><span class="sxs-lookup"><span data-stu-id="b414a-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="b414a-189">例如，可以在上运行它 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ：</span><span class="sxs-lookup"><span data-stu-id="b414a-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="b414a-190">然后，打印输出</span><span class="sxs-lookup"><span data-stu-id="b414a-190">The printed output is then</span></span>

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

<span data-ttu-id="b414a-191">有关这些指标的含义的详细信息，请参阅 [Resource 估计器：报告的度量值](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)。</span><span class="sxs-lookup"><span data-stu-id="b414a-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="b414a-192">命令行执行摘要</span><span class="sxs-lookup"><span data-stu-id="b414a-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="b414a-193">非 Q# `dotnet run` 选项</span><span class="sxs-lookup"><span data-stu-id="b414a-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="b414a-194">如上所述 `--project` ，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)还接受与可调用参数无关的选项 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="b414a-195">如果同时提供这两种选项，则 `dotnet` 必须先提供特定于的选项，然后再提供分隔符 `--` ，然后 Q# 选择特定的选项。</span><span class="sxs-lookup"><span data-stu-id="b414a-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="b414a-196">例如，指定将路径与上述操作的数字 qubits 一起执行 `dotnet run --project <PATH> -- -n <n>` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="b414a-197">Q# 具有主机程序</span><span class="sxs-lookup"><span data-stu-id="b414a-197">Q# with host programs</span></span>

<span data-ttu-id="b414a-198">使用我们的 Q# 文件，从命令提示符直接调用操作或函数的替代方法是使用另一种传统语言的 *主机程序* 。</span><span class="sxs-lookup"><span data-stu-id="b414a-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="b414a-199">具体而言，可以使用 Python 或 .NET 语言（如 c # 或 F # (）实现此目的。为了简单起见，我们只会在此处) 详细说明 c #。</span><span class="sxs-lookup"><span data-stu-id="b414a-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="b414a-200">若要启用互操作性，还需要进行一些设置，但这些详细信息可在 [安装指南](xref:microsoft.quantum.install)中找到。</span><span class="sxs-lookup"><span data-stu-id="b414a-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b414a-201">简而言之，这种情况下，这种情况下包括主机程序文件 (例如， `*.py` 或 `*.cs`) 在与文件相同的位置 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="b414a-202">它现在是运行的 *主机* 程序，在执行过程中，它可以 Q# 从文件调用特定的操作和函数 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="b414a-203">互操作性的核心基于 Q# 编译器使文件内容可供 Q# 主机程序访问，以便可以调用。</span><span class="sxs-lookup"><span data-stu-id="b414a-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="b414a-204">使用主机程序的一个主要优点是， Q# 可以使用主机语言进一步处理程序返回的传统数据。</span><span class="sxs-lookup"><span data-stu-id="b414a-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="b414a-205">这可能包括一些高级的数据处理 (例如，不能在内部执行 Q#) ，然后 Q# 基于这些结果调用更多操作，也可以像绘制结果那样简单 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="b414a-206">此处显示了一般方案，并讨论了下面的 Python 和 c # 的具体实现。</span><span class="sxs-lookup"><span data-stu-id="b414a-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="b414a-207">有关使用 F # 宿主程序的示例，请参阅 [.net 互操作性示例](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)。</span><span class="sxs-lookup"><span data-stu-id="b414a-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="b414a-208">用于 `@EntryPoint()` Q# 应用程序的属性不能与主机程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="b414a-208">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="b414a-209">如果主机正在调用的文件中存在错误，则会引发错误 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="b414a-210">若要使用不同的主机程序，不需要对文件进行任何更改 `*.qs` Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="b414a-211">以下主机程序实现均使用相同的 Q# 文件：</span><span class="sxs-lookup"><span data-stu-id="b414a-211">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="b414a-212">选择与您感兴趣的主机语言对应的选项卡。</span><span class="sxs-lookup"><span data-stu-id="b414a-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="b414a-213">Python</span><span class="sxs-lookup"><span data-stu-id="b414a-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="b414a-214">Python 主机计划如下所示：</span><span class="sxs-lookup"><span data-stu-id="b414a-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="b414a-215">导入 `qsharp` 模块，该模块将注册模块加载程序以实现 Q# 互操作性。</span><span class="sxs-lookup"><span data-stu-id="b414a-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="b414a-216">这允许 Q# 命名空间显示为 Python 模块，我们可以将其 "导入" callables "导入" Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="b414a-217">请注意，从技术上讲，它并不是 Q# 导入的 callables 本身，而是允许调用它们的 Python 存根。</span><span class="sxs-lookup"><span data-stu-id="b414a-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="b414a-218">然后，它们将作为 Python 类的对象，使用方法指定要为执行操作而发送操作的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="b414a-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="b414a-219">导入这些 Q# callables，我们将在此示例中直接调用--- `MeasureSuperposition` 和 `MeasureSuperpositionArray` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="b414a-220">`qsharp`导入模块后，还可以直接从 Q# 库命名空间导入 callables。</span><span class="sxs-lookup"><span data-stu-id="b414a-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="b414a-221">在其他任何 Python 代码中，现在可以在特定目标计算机上调用这些 callables，并将其返回值分配给变量 (如果它们返回值) 以便进一步使用。</span><span class="sxs-lookup"><span data-stu-id="b414a-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="b414a-222">指定目标计算机</span><span class="sxs-lookup"><span data-stu-id="b414a-222">Specifying target machines</span></span>
<span data-ttu-id="b414a-223">调用要在特定目标计算机上运行的操作是通过导入的对象上的不同 Python 方法完成的。</span><span class="sxs-lookup"><span data-stu-id="b414a-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="b414a-224">例如， `.simulate(<args>)` 使用 `QuantumSimulator` 运行操作，而 `.estimate_resources(<args>)` 在上执行此操作 `ResourcesEstimator` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="b414a-225">向 Q 传递输入\#</span><span class="sxs-lookup"><span data-stu-id="b414a-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="b414a-226">Q#应以关键字参数的形式提供可调用的参数，其中，关键字是可调用定义中的参数名称 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="b414a-227">这是 `MeasureSuperpositionArray.simulate(n=4)` 有效的，但 `MeasureSuperpositionArray.simulate(4)` 会引发错误。</span><span class="sxs-lookup"><span data-stu-id="b414a-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="b414a-228">因此，Python 主机程序</span><span class="sxs-lookup"><span data-stu-id="b414a-228">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="b414a-229">生成如下所示的输出：</span><span class="sxs-lookup"><span data-stu-id="b414a-229">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="b414a-230">使用 Q# 其他项目或包中的代码</span><span class="sxs-lookup"><span data-stu-id="b414a-230">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="b414a-231">默认情况下，该 `import qsharp` 命令 `.qs` 会加载当前文件夹中的所有文件，并使其 Q# 操作和函数可供在 Python 脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="b414a-231">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="b414a-232">若要 Q# 从其他文件夹加载代码，可以使用[ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects)来添加对项目的引用 `.csproj` Q# (即引用) 的项目 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-232">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="b414a-233">此命令将编译 `.qs` 包含及其子文件夹的文件夹中的任何文件 `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-233">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="b414a-234">它还会以递归方式加载通过 `PackageReference` 或 Q# 通过该文件引用的项目引用的任何包 `ProjectReference` `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-234">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="b414a-235">例如，以下 Python 代码将导入外部项目，并引用其相对于当前文件夹的路径，并调用其 Q# 操作之一：</span><span class="sxs-lookup"><span data-stu-id="b414a-235">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="b414a-236">这会生成类似于以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="b414a-236">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="b414a-237">若要加载包含代码的外部包 Q# ，请使用[ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)。</span><span class="sxs-lookup"><span data-stu-id="b414a-237">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="b414a-238">如果 Q# 当前文件夹中的代码依赖于外部项目或包，则在运行时可能会看到错误 `import qsharp` ，因为尚未加载依赖关系。</span><span class="sxs-lookup"><span data-stu-id="b414a-238">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="b414a-239">若要在命令期间加载所需的外部包或 Q# 项目 `import qsharp` ，请确保具有 Python 脚本的文件夹包含 `.csproj` 引用的文件 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-239">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="b414a-240">在这种情况 `.csproj` 下，将属性添加 `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` 到中 `<PropertyGroup>` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-240">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="b414a-241">这将指示我在 Q# 命令过程中以递归方式加载 `ProjectReference` `PackageReference` 在中找到的任何或项 `.csproj` `import qsharp` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-241">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="b414a-242">例如，下面是一个简单的 `.csproj` 文件，该文件将导致 Q# 自动加载 `Microsoft.Quantum.Chemistry` 包：</span><span class="sxs-lookup"><span data-stu-id="b414a-242">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

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
> <span data-ttu-id="b414a-243">目前， `<IQSharpLoadAutomatically>` python 主机需要此自定义属性，但在将来，这可能会成为与 `.csproj` Python 脚本位于同一文件夹中的文件的默认行为。</span><span class="sxs-lookup"><span data-stu-id="b414a-243">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="b414a-244">目前， `<QsharpCompile>` `.csproj` Python 主机会忽略中的设置，并且 `.qs` 加载并编译 (的文件夹中的所有文件 `.csproj` （包括子文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="b414a-244">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="b414a-245">`.csproj`以后将改进对设置的支持 (参阅[iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277)了解更多详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="b414a-245">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="b414a-246">C#</span><span class="sxs-lookup"><span data-stu-id="b414a-246">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b414a-247">C # 主机程序具有多个组件，并与 QDK 的某些组件（如模拟器）非常紧密，这些组件是在 c # 的基础上构建的。</span><span class="sxs-lookup"><span data-stu-id="b414a-247">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="b414a-248">Q#编译器在此处通过 Q# 在文件的命名空间中生成一个等效的 c # 命名空间来工作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-248">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="b414a-249">它针对其中定义的每个 callables 或类型进一步生成一个等效的命名 c # 类 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-249">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="b414a-250">首先，我们将在主机程序中使用的类与语句一起使用 `using` ，这些语句大致类似于 `open` 文件中的语句 Q# ：</span><span class="sxs-lookup"><span data-stu-id="b414a-250">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="b414a-251">接下来，我们声明 c # 命名空间，一些其他位和部分 (查看以下完整的代码块) ，然后需要 (如计算 callables) 的参数。 Q#</span><span class="sxs-lookup"><span data-stu-id="b414a-251">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="b414a-252">在本例中，后者不是必需的，但在  [.net 互操作性示例](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)中可以找到此类用法的示例。</span><span class="sxs-lookup"><span data-stu-id="b414a-252">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="b414a-253">目标计算机</span><span class="sxs-lookup"><span data-stu-id="b414a-253">Target machines</span></span>

<span data-ttu-id="b414a-254">返回到 Q# ，我们必须创建将对其执行操作的任何目标计算机的实例。</span><span class="sxs-lookup"><span data-stu-id="b414a-254">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="b414a-255">使用其他目标计算机非常简单，只需要实例化不同的计算机，但执行此操作和处理返回的方式可能略有不同。</span><span class="sxs-lookup"><span data-stu-id="b414a-255">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="b414a-256">为简洁起见，我们现在坚持到 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ，并包括 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [以下](#including-the-resources-estimator)。</span><span class="sxs-lookup"><span data-stu-id="b414a-256">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="b414a-257">每个从操作生成的 c # 类 Q# 都有一个 `Run` 方法，第一个参数必须是目标计算机实例。</span><span class="sxs-lookup"><span data-stu-id="b414a-257">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="b414a-258">因此，若要 `MeasureSuperposition` 在上运行 `QuantumSimulator` ，我们将使用 `MeasureSuperposition.Run(sim)` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-258">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="b414a-259">然后，可以将返回的结果分配给 c # 中的变量：</span><span class="sxs-lookup"><span data-stu-id="b414a-259">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="b414a-260">`Run`此方法是异步执行的，因为这将是真实量程硬件的情况，因此， `await` 关键字会阻止进一步执行，直到任务完成。</span><span class="sxs-lookup"><span data-stu-id="b414a-260">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="b414a-261">如果可 Q# 调用的不包含任何返回 (即) 返回类型 `Unit` ，则仍可通过相同的方式执行该操作，而无需将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="b414a-261">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="b414a-262">在这种情况下，整行只包含</span><span class="sxs-lookup"><span data-stu-id="b414a-262">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="b414a-263">自变量</span><span class="sxs-lookup"><span data-stu-id="b414a-263">Arguments</span></span>

<span data-ttu-id="b414a-264">可调用的任何参数 Q# 只是作为附加参数传递叫目标计算机。</span><span class="sxs-lookup"><span data-stu-id="b414a-264">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="b414a-265">因此， `MeasureSuperpositionArray` qubits 上的结果 `n=4` 将通过</span><span class="sxs-lookup"><span data-stu-id="b414a-265">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="b414a-266">因此，完整的 c # 宿主程序可能类似于</span><span class="sxs-lookup"><span data-stu-id="b414a-266">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="b414a-267">在 c # 文件的位置，通过输入，可以从命令提示符运行主机程序</span><span class="sxs-lookup"><span data-stu-id="b414a-267">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="b414a-268">在这种情况下，你将看到写入到控制台的输出，类似于</span><span class="sxs-lookup"><span data-stu-id="b414a-268">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="b414a-269">由于编译器与命名空间的互操作性，因此，我们可以 Q# 在不使用语句的情况下让 callables 可用 `using NamespaceName;` ，并且只需将 c # 命名空间标题与它进行匹配即可。</span><span class="sxs-lookup"><span data-stu-id="b414a-269">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="b414a-270">也就是说，将替换 `namespace host` 为 `namespace NamespaceName` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-270">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="b414a-271">包括资源估计器</span><span class="sxs-lookup"><span data-stu-id="b414a-271">Including the resources estimator</span></span>

<span data-ttu-id="b414a-272">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)需要略有不同的实现来检索输出。</span><span class="sxs-lookup"><span data-stu-id="b414a-272">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="b414a-273">首先，不会将它们实例化为带有语句的变量 `using` (与 `QuantumSimulator`) 一样，我们通过</span><span class="sxs-lookup"><span data-stu-id="b414a-273">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="b414a-274">请注意， Q# 我们已为每个操作实例化一个目标模拟器，而不是由多个操作使用单个目标模拟器。</span><span class="sxs-lookup"><span data-stu-id="b414a-274">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="b414a-275">这是因为在用作目标计算机时，对象本身会被修改，然后可以使用类方法在以后检索这些对象的结果 `.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-275">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="b414a-276">若要在资源估算上运行操作，请使用</span><span class="sxs-lookup"><span data-stu-id="b414a-276">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="b414a-277">然后，将结果作为制表符分隔的值（ (TSV) 与和一起提取 `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-277">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="b414a-278">因此，使用和的完整 c # 宿主程序 `QuantumSimulator` `ResourcesEstimator` 可以采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="b414a-278">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="b414a-279">这会生成类似于的输出</span><span class="sxs-lookup"><span data-stu-id="b414a-279">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="b414a-280">Q# Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="b414a-280">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="b414a-281">Q# Jupyter 笔记本利用 I Q# 内核，使你能够在单个笔记本中定义、编译和运行 Q# callables，---所有说明、注释和其他内容。</span><span class="sxs-lookup"><span data-stu-id="b414a-281">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="b414a-282">这意味着，虽然可以导入和使用文件的内容，但 `*.qs` Q# 它们在执行模型中不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b414a-282">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="b414a-283">在这里，我们将详细介绍如何运行 Q# 上面定义的操作，但 Q# 在 [简介 Q# 和 Jupyter 笔记本](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)中提供了有关使用 Jupyter 笔记本的更广泛的介绍。</span><span class="sxs-lookup"><span data-stu-id="b414a-283">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="b414a-284">定义操作</span><span class="sxs-lookup"><span data-stu-id="b414a-284">Defining operations</span></span>

<span data-ttu-id="b414a-285">在 Q# Jupyter Notebook 中，你可以 Q# 像在文件的命名空间内一样输入代码 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b414a-285">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="b414a-286">因此，可以从具有相应命名空间的语句的[ Q# 标准库](xref:microsoft.quantum.qsharplibintro)中启用对 callables 的访问 `open` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-286">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="b414a-287">使用此类语句运行单元时，这些命名空间中的定义在整个工作区中都可用。</span><span class="sxs-lookup"><span data-stu-id="b414a-287">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="b414a-288">Callables 和[Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) [Canon](xref:microsoft.quantum.canon) (（例如 [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ）和) 自动可用于 Jupyter 笔记本的单元中定义的操作。 Q#</span><span class="sxs-lookup"><span data-stu-id="b414a-288">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="b414a-289">不过，对于从外部源文件引入的代码)  (，这种情况并不是如此 Q# 。 [ Q# ](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)</span><span class="sxs-lookup"><span data-stu-id="b414a-289">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="b414a-290">同样，定义操作只需编写 Q# 代码并运行单元。</span><span class="sxs-lookup"><span data-stu-id="b414a-290">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="b414a-291">然后，输出会列出这些操作，随后可以从未来的单元格中调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="b414a-291">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="b414a-292">目标计算机</span><span class="sxs-lookup"><span data-stu-id="b414a-292">Target machines</span></span>

<span data-ttu-id="b414a-293">通过 [I Q# 幻命令](xref:microsoft.quantum.guide.quickref.iqsharp)提供在特定目标计算机上运行操作的功能。</span><span class="sxs-lookup"><span data-stu-id="b414a-293">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="b414a-294">例如， `%simulate` 利用 `QuantumSimulator` ，并 `%estimate` 使用 `ResourcesEstimator` ：</span><span class="sxs-lookup"><span data-stu-id="b414a-294">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="b414a-295">将输入传递到函数和操作</span><span class="sxs-lookup"><span data-stu-id="b414a-295">Passing inputs to functions and operations</span></span>

<span data-ttu-id="b414a-296">若要将输入传递到 Q# 操作，可以将参数作为 `key=value` 配对传递到执行幻命令。</span><span class="sxs-lookup"><span data-stu-id="b414a-296">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the execution magic command.</span></span>
<span data-ttu-id="b414a-297">因此，若要运行 `MeasureSuperpositionArray` 四个 qubits，可以运行 `%simulate MeasureSuperpositionArray n=4` ：</span><span class="sxs-lookup"><span data-stu-id="b414a-297">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="b414a-298">此模式可与 `%estimate` 和其他执行命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="b414a-298">This pattern can be used similarly with `%estimate` and other execution commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="b414a-299">使用 Q# 其他项目或包中的代码</span><span class="sxs-lookup"><span data-stu-id="b414a-299">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="b414a-300">默认情况下， Q# Jupyter Notebook 加载 `.qs` 当前文件夹中的所有文件，并使其 Q# 操作和函数可从笔记本内部使用。</span><span class="sxs-lookup"><span data-stu-id="b414a-300">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="b414a-301">[ `%who` 魔术命令](xref:microsoft.quantum.iqsharp.magic-ref.who)列出了当前可用的所有 Q# 操作和函数。</span><span class="sxs-lookup"><span data-stu-id="b414a-301">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="b414a-302">若要 Q# 从另一个文件夹加载代码，可以使用[ `%project` 魔棒命令](xref:microsoft.quantum.iqsharp.magic-ref.project)为项目添加对 `.csproj` 文件的引用 Q# (即引用) 的项目 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-302">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="b414a-303">此命令将编译 `.qs` 包含 `.csproj`) 的 (和子文件夹的文件夹中的任何文件。</span><span class="sxs-lookup"><span data-stu-id="b414a-303">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="b414a-304">它还会以递归方式加载通过 `PackageReference` 或 Q# 通过该文件引用的项目引用的任何包 `ProjectReference` `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-304">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="b414a-305">例如，下面的单元模拟了 Q# 外部项目中的操作，该项目路径相对于当前文件夹引用：</span><span class="sxs-lookup"><span data-stu-id="b414a-305">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="b414a-306">若要加载包含 Q# 代码的外部包，请使用[ `%package` 魔棒命令](xref:microsoft.quantum.iqsharp.magic-ref.package)。</span><span class="sxs-lookup"><span data-stu-id="b414a-306">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="b414a-307">加载包还会使任何自定义的幻命令或显示包含在包中的任何程序集中的编码器。</span><span class="sxs-lookup"><span data-stu-id="b414a-307">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="b414a-308">若要 Q# 在笔记本初始化时加载外部包或项目，请确保笔记本文件夹包含 `.csproj` 引用的文件 `Microsoft.Quantum.Sdk` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-308">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="b414a-309">在这种情况 `.csproj` 下，将属性添加 `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` 到中 `<PropertyGroup>` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-309">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="b414a-310">这将指示我 Q# 以递归方式加载 `ProjectReference` `PackageReference` 在笔记本加载时在中找到的任何或项 `.csproj` 。</span><span class="sxs-lookup"><span data-stu-id="b414a-310">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="b414a-311">例如，下面是一个简单的 `.csproj` 文件，该文件将导致 Q# 自动加载 `Microsoft.Quantum.Chemistry` 包：</span><span class="sxs-lookup"><span data-stu-id="b414a-311">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

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
> <span data-ttu-id="b414a-312">目前 `<IQSharpLoadAutomatically>` Jupyter Notebook 主机需要此自定义属性 Q# ，但在将来，这可能会成为与 `.csproj` 笔记本文件位于同一文件夹中的文件的默认行为。</span><span class="sxs-lookup"><span data-stu-id="b414a-312">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="b414a-313">目前 `<QsharpCompile>` `.csproj` Jupyter Notebook 主机忽略中的设置 Q# ，并且 `.qs` 加载和编译 (的文件夹中的所有文件 `.csproj` （包括子) 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="b414a-313">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="b414a-314">`.csproj`以后将改进对设置的支持 (参阅[iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277)了解更多详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="b414a-314">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
