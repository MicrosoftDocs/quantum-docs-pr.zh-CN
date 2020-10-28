---
title: 测试和调试
description: 了解如何使用单元测试、事实和断言以及转储函数来测试和调试量程程序。
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690962"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="90f9f-103">测试和调试</span><span class="sxs-lookup"><span data-stu-id="90f9f-103">Testing and debugging</span></span>

<span data-ttu-id="90f9f-104">与传统编程一样，必须能够检查量子程序是否按预期方式操作，并且能够诊断不正确的行为。</span><span class="sxs-lookup"><span data-stu-id="90f9f-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="90f9f-105">在本部分中，我们介绍了 :::no-loc(Q#)::: 用于测试和调试量程程序的工具。</span><span class="sxs-lookup"><span data-stu-id="90f9f-105">In this section, we cover the tools offered by :::no-loc(Q#)::: for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="90f9f-106">单元测试</span><span class="sxs-lookup"><span data-stu-id="90f9f-106">Unit Tests</span></span>

<span data-ttu-id="90f9f-107">测试传统程序的一种常见方法是编写称为 *单元测试* 的小程序，这些程序在库中运行代码，并将其输出与某个预期输出进行比较。</span><span class="sxs-lookup"><span data-stu-id="90f9f-107">One common approach to testing classical programs is to write small programs called *unit tests* , which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="90f9f-108">例如，你可以确保返回， `Square(2)` `4` 因为你知道 $ 2 ^ 2 = $4 的 *先验* 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="90f9f-109">:::no-loc(Q#)::: 支持为量程程序创建单元测试，并且该测试可以作为测试在 [xUnit](https://xunit.github.io/) 单元测试框架中运行。</span><span class="sxs-lookup"><span data-stu-id="90f9f-109">:::no-loc(Q#)::: supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="90f9f-110">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="90f9f-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="90f9f-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="90f9f-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="90f9f-112">打开 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="90f9f-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="90f9f-113">请在 " **文件** " 菜单中选择 " **新建 > 项目 ...** "。在右上角，搜索 `:::no-loc(Q#):::` ，然后选择 " **:::no-loc(Q#)::: 测试项目** " 模板。</span><span class="sxs-lookup"><span data-stu-id="90f9f-113">Go to the **File** menu and select **New > Project...** . In the upper right corner, search for `:::no-loc(Q#):::`, and select the **:::no-loc(Q#)::: Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="90f9f-114">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="90f9f-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="90f9f-115">从你喜欢的命令行运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="90f9f-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang :::no-loc(Q#)::: -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="90f9f-116">你的新项目有一个文件 `Tests.qs` ，它提供了一个用于定义新单元测试的便利位置 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new :::no-loc(Q#)::: unit tests.</span></span>
<span data-ttu-id="90f9f-117">最初，此文件包含一个示例单元测试， `AllocateQubit` 该测试检查新分配的 qubit 是否处于 $ \ket {0} $ 状态并输出一条消息：</span><span class="sxs-lookup"><span data-stu-id="90f9f-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="90f9f-118">:::no-loc(Q#):::采用类型为的参数和返回的任何操作或函数 `Unit` `Unit` 都可以通过属性标记为单元测试 `@Test("...")` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-118">Any :::no-loc(Q#)::: operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="90f9f-119">在上面的示例中，该属性的参数（ `"QuantumSimulator"` ）指定测试运行的目标。</span><span class="sxs-lookup"><span data-stu-id="90f9f-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="90f9f-120">单个测试可以在多个目标上运行。</span><span class="sxs-lookup"><span data-stu-id="90f9f-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="90f9f-121">例如，在之前添加一个 `@Test("ResourcesEstimator")` 属性 `AllocateQubit` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="90f9f-122">保存该文件并运行所有测试。</span><span class="sxs-lookup"><span data-stu-id="90f9f-122">Save the file and run all tests.</span></span> <span data-ttu-id="90f9f-123">现在应有两个单元测试，一个在 `AllocateQubit` 上运行，另一个 `QuantumSimulator` 在上运行 `ResourcesEstimator` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="90f9f-124">:::no-loc(Q#):::编译器可识别内置目标 `"QuantumSimulator"` 、 `"ToffoliSimulator"` 和， `"ResourcesEstimator"` 作为单元测试的有效运行目标。</span><span class="sxs-lookup"><span data-stu-id="90f9f-124">The :::no-loc(Q#)::: compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="90f9f-125">还可以指定任何完全限定的名称来定义自定义的运行目标。</span><span class="sxs-lookup"><span data-stu-id="90f9f-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="90f9f-126">运行 :::no-loc(Q#)::: 单元测试</span><span class="sxs-lookup"><span data-stu-id="90f9f-126">Running :::no-loc(Q#)::: Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="90f9f-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="90f9f-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="90f9f-128">作为一次性的每个解决方案设置，请在 " **测试** " 菜单中，选择 " **测试设置" > 默认处理器体系结构 > X64** 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64** .</span></span>

> [!TIP]
> <span data-ttu-id="90f9f-129">Visual Studio 的默认处理器结构设置存储在解决方案选项 (`.suo` 每个解决方案) 文件中。</span><span class="sxs-lookup"><span data-stu-id="90f9f-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="90f9f-130">如果删除此文件，则需要再次选择 **X64** 作为处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="90f9f-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="90f9f-131">生成项目，打开 " **测试** " 菜单，然后选择 " **Windows > 测试资源管理器** "。</span><span class="sxs-lookup"><span data-stu-id="90f9f-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer** .</span></span> <span data-ttu-id="90f9f-132">**AllocateQubit** 在 " **未运行的测试** " 组中的测试列表中显示。</span><span class="sxs-lookup"><span data-stu-id="90f9f-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="90f9f-133">选择 " **全部运行** " 或 "运行此单个测试"。</span><span class="sxs-lookup"><span data-stu-id="90f9f-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="90f9f-134">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="90f9f-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="90f9f-135">若要运行测试，请导航到包含) 的文件夹 (项目文件夹 `Tests.csproj` ，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="90f9f-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="90f9f-136">应会看到类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="90f9f-136">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="90f9f-137">可以根据其名称或运行目标筛选单元测试：</span><span class="sxs-lookup"><span data-stu-id="90f9f-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="90f9f-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="90f9f-138">\*\*_</span></span>

<span data-ttu-id="90f9f-139">内部函数 <xref:Microsoft.Quantum.Intrinsic.Message> 具有类型 `(String -> Unit)` ，并支持创建诊断消息。</span><span class="sxs-lookup"><span data-stu-id="90f9f-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="90f9f-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="90f9f-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="90f9f-141">在测试资源管理器中运行测试并单击测试后，将显示一个面板，其中包含有关测试运行的信息：通过/失败状态、运行时间和输出链接。</span><span class="sxs-lookup"><span data-stu-id="90f9f-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="90f9f-142">单击 "_ *输出* \*" 可在新窗口中打开测试输出。</span><span class="sxs-lookup"><span data-stu-id="90f9f-142">Click _ *Output* \* to open the test output in a new window.</span></span>

![测试输出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="90f9f-144">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="90f9f-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="90f9f-145">每个测试的通过/失败状态将由打印到控制台 `dotnet test` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="90f9f-146">对于失败的测试，还会将输出输出到控制台，以帮助诊断故障。</span><span class="sxs-lookup"><span data-stu-id="90f9f-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="90f9f-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="90f9f-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="90f9f-148">事实和断言</span><span class="sxs-lookup"><span data-stu-id="90f9f-148">Facts and Assertions</span></span>

<span data-ttu-id="90f9f-149">因为中的函数没有 :::no-loc(Q#)::: 任何 _逻辑_ 副作用，所以，你永远不会观察到 :::no-loc(Q#)::: 程序中的任何其他类型的效果，因为它运行的函数的输出类型为空元组 `()` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-149">Because functions in :::no-loc(Q#)::: have no _logical_ side effects, you can never observe, from within a :::no-loc(Q#)::: program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="90f9f-150">也就是说，目标计算机可以选择不运行返回的任何函数， `()` 保证此省略不会修改任何以下代码的行为 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following :::no-loc(Q#)::: code.</span></span>
<span data-ttu-id="90f9f-151">此行为使函数返回 `()` (如 `Unit`) 用于将断言和调试逻辑嵌入到程序中的有用工具 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into :::no-loc(Q#)::: programs.</span></span> 

<span data-ttu-id="90f9f-152">我们来看一个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="90f9f-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="90f9f-153">此处，关键字 `fail` 指示计算不应继续，并在运行程序的目标计算机上引发异常 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the :::no-loc(Q#)::: program.</span></span>
<span data-ttu-id="90f9f-154">按照定义，无法从内观察到此类故障 :::no-loc(Q#)::: ，因为目标计算机在 :::no-loc(Q#)::: 到达语句后不再运行代码 `fail` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-154">By definition, a failure of this kind cannot be observed from within :::no-loc(Q#):::, as the target machine no longer runs the :::no-loc(Q#)::: code after reaching a `fail` statement.</span></span>
<span data-ttu-id="90f9f-155">因此，如果我们继续通过调用，则 `PositivityFact` 可以确保其输入为正值。</span><span class="sxs-lookup"><span data-stu-id="90f9f-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="90f9f-156">请注意，我们可以实现与 `PositivityFact` [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) 从命名空间中使用函数相同的行为 <xref:Microsoft.Quantum.Diagnostics> ：</span><span class="sxs-lookup"><span data-stu-id="90f9f-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="90f9f-157">另一方面，_Assertions \* 与事实类似，但可能依赖于目标计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="90f9f-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="90f9f-158">它们相应地定义为操作，而事实定义为函数 (如前面的示例) 中所示。</span><span class="sxs-lookup"><span data-stu-id="90f9f-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="90f9f-159">若要理解这一区别，请考虑在断言内使用以下事实：</span><span class="sxs-lookup"><span data-stu-id="90f9f-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="90f9f-160">在这里，我们将使用操作 <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> 来返回可供使用的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="90f9f-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="90f9f-161">因为这取决于程序及其运行环境的全局状态，所以，的定义 `AssertQubitsAreAvailable` 必须也是操作。</span><span class="sxs-lookup"><span data-stu-id="90f9f-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="90f9f-162">但是，我们可以使用该全局状态生成简单 `Bool` 值作为函数的输入 `Fact` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="90f9f-163">基于这些观点构建[的 prelude](xref:microsoft.quantum.libraries.standard.prelude)提供两个特别有用的断言， <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 并 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 作为操作建模 `()` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="90f9f-164">这些断言每个都采用一个 Pauli 运算符，该运算符描述特定的感兴趣的度量、在其上执行度量的量程注册，以及一个假设结果。</span><span class="sxs-lookup"><span data-stu-id="90f9f-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="90f9f-165">模拟使用的目标计算机不受非 [克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的约束，并且可以在不干扰传递到此类断言的寄存器的情况下执行此类测量。</span><span class="sxs-lookup"><span data-stu-id="90f9f-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="90f9f-166">然后，模拟器可以类似于 `PositivityFact` previous 函数，如果在实践中未发现假设结果，则停止计算：</span><span class="sxs-lookup"><span data-stu-id="90f9f-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in :::no-loc(Q#):::,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="90f9f-167">在物理量程硬件上，非克隆定理阻止对量程状态的检查， `AssertMeasurement` 且和 `AssertMeasurementProbability` 操作只返回， `()` 不会产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="90f9f-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="90f9f-168"><xref:Microsoft.Quantum.Diagnostics>命名空间提供了更多系列功能 `Assert` ，您可以在其中查看更高级的条件。</span><span class="sxs-lookup"><span data-stu-id="90f9f-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="90f9f-169">转储函数</span><span class="sxs-lookup"><span data-stu-id="90f9f-169">Dump Functions</span></span>

<span data-ttu-id="90f9f-170">为了帮助解决量程程序问题， <xref:Microsoft.Quantum.Diagnostics> 命名空间提供了两个函数，可将目标计算机的当前状态转储到文件： <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 和 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="90f9f-171">每个生成的输出依赖于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="90f9f-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="90f9f-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="90f9f-172">DumpMachine</span></span>

<span data-ttu-id="90f9f-173">作为量程开发工具包的一部分分发的全状态量程模拟器会将整个量程系统的 [波形函数](https://en.wikipedia.org/wiki/Wave_function) 写入文件中，这是一维复数数组，其中每个元素都表示度量计算基础状态 $ \ket{n} $ 的概率的波幅，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $ b_i $ b_1b_0} \{ $ \} 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="90f9f-174">例如，在仅分配了两个 qubits 并在量程状态 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } \ket 中的计算机上 {2} {10} ，\end{align} $ $ 调用将 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="90f9f-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="90f9f-175">第一行提供了一个注释，其中包含相应 qubits 的 id。</span><span class="sxs-lookup"><span data-stu-id="90f9f-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="90f9f-176">其余行说明了度量基准状态向量 $ \ket{n} $ 在笛卡尔和极坐标中的概率幅度。</span><span class="sxs-lookup"><span data-stu-id="90f9f-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="90f9f-177">对于第一行，详细信息：</span><span class="sxs-lookup"><span data-stu-id="90f9f-177">In detail for the first row:</span></span>

* <span data-ttu-id="90f9f-178">**`∣0❭:`** 该行与 `0` 计算基础状态相对应</span><span class="sxs-lookup"><span data-stu-id="90f9f-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="90f9f-179">**`0.707107 +  0.000000 i`** ：以笛卡尔格式的概率幅度。</span><span class="sxs-lookup"><span data-stu-id="90f9f-179">**`0.707107 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="90f9f-180">**` == `** ： `equal` 符号分隔等效表示形式。</span><span class="sxs-lookup"><span data-stu-id="90f9f-180">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="90f9f-181">**`**********  `** ：大小的图形表示形式，的数量与 `*` 度量此状态向量的概率成正比。</span><span class="sxs-lookup"><span data-stu-id="90f9f-181">**`**********  `** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="90f9f-182">**`[ 0.500000 ]`** ：量值的数值</span><span class="sxs-lookup"><span data-stu-id="90f9f-182">**`[ 0.500000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="90f9f-183">**`    ---`** ：振幅阶段的图形表示形式 (参阅以下输出) 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-183">**`    ---`** : A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="90f9f-184">**`[ 0.0000 rad ]`** ：相位 (的数值) 以弧度表示。</span><span class="sxs-lookup"><span data-stu-id="90f9f-184">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="90f9f-185">大小和阶段都以图形表示形式显示。</span><span class="sxs-lookup"><span data-stu-id="90f9f-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="90f9f-186">大小表示形式是一种直截了当的：它显示一个条形 `*` ，这越大越大。</span><span class="sxs-lookup"><span data-stu-id="90f9f-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="90f9f-187">对于阶段，我们将显示以下符号，以表示基于范围的角度：</span><span class="sxs-lookup"><span data-stu-id="90f9f-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="90f9f-188">以下示例演示 `DumpMachine` 了一些常见状态：</span><span class="sxs-lookup"><span data-stu-id="90f9f-188">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="90f9f-189">Qubit 的 id 在运行时分配，不一定与 qubit 的分配顺序或其在 qubit 寄存器中的位置一致。</span><span class="sxs-lookup"><span data-stu-id="90f9f-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="90f9f-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="90f9f-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="90f9f-191">可以通过在代码中放置一个断点并检查 qubit 变量的值，在 Visual Studio 中查找 qubit id，例如：</span><span class="sxs-lookup"><span data-stu-id="90f9f-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在 Visual Studio 中显示 qubit id](~/media/qubit_id.png)
  >
  > <span data-ttu-id="90f9f-193">带有索引的 qubit `0` `register2` id =，具有 `3` 索引的 qubit 的 `1` id = `2` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="90f9f-194">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="90f9f-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="90f9f-195">您可以使用函数查找 qubit id， <xref:Microsoft.Quantum.Intrinsic.Message> 并在消息中传递 qubit 变量，例如：</span><span class="sxs-lookup"><span data-stu-id="90f9f-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="90f9f-196">这可能会生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="90f9f-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="90f9f-197">这意味着，具有索引的 qubit `0` `register2` id =，具有 `3` 索引的 qubit 的 `1` id = `2` 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="90f9f-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="90f9f-198">\*\*_</span></span>

<span data-ttu-id="90f9f-199">由于 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 是  <xref:Microsoft.Quantum.Diagnostics> 命名空间的一部分，因此必须添加 `open` 语句来访问它：</span><span class="sxs-lookup"><span data-stu-id="90f9f-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="90f9f-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="90f9f-200">DumpRegister</span></span>

<span data-ttu-id="90f9f-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> 的工作方式类似 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ，不同之处在于它还采用 qubits 数组，以将信息量限制为仅与对应 qubits 相关。</span><span class="sxs-lookup"><span data-stu-id="90f9f-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="90f9f-202">与一样 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ，生成的信息 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 取决于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="90f9f-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="90f9f-203">对于全状态量程模拟器，它会将波形功能写入文件，使其与所提供的 qubits 生成的量程子系统的全局阶段完全相同，格式与相同 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="90f9f-204">例如，再次使计算机只分配了两个 qubits，并在量程状态 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } {2} \ket {10} =-e ^ {-i \ pi/4} ( ( \frac {1} {\sqrt {2} } \ket {0} -\frac{ (1 + i) {2} } \ket {1} ) \otimes \frac{- ({2} {0} \end{align} $ $ 调用 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 来 `qubit[0]` 生成此输出：</span><span class="sxs-lookup"><span data-stu-id="90f9f-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="90f9f-205">和的调用将 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> `qubit[1]` 生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="90f9f-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="90f9f-206">通常，与另一寄存器放大的寄存器的状态为混合状态，而不是纯状态。</span><span class="sxs-lookup"><span data-stu-id="90f9f-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="90f9f-207">在这种情况下，会 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 输出以下消息：</span><span class="sxs-lookup"><span data-stu-id="90f9f-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="90f9f-208">下面的示例演示如何 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 在代码中使用和 :::no-loc(Q#)::: ：</span><span class="sxs-lookup"><span data-stu-id="90f9f-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your :::no-loc(Q#)::: code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="90f9f-209">调试</span><span class="sxs-lookup"><span data-stu-id="90f9f-209">Debugging</span></span>

<span data-ttu-id="90f9f-210">在 `Assert` 和 `Dump` 函数和操作的基础上， :::no-loc(Q#)::: 支持标准 Visual Studio 调试功能的子集： [设置行断点](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [使用 F10 逐句通过代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)，以及在模拟器上运行代码时，可以 [检查经典变量的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) 。</span><span class="sxs-lookup"><span data-stu-id="90f9f-210">On top of `Assert` and `Dump` functions and operations, :::no-loc(Q#)::: supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="90f9f-211">Visual Studio Code 中的调试利用了 c # 提供的调试功能作为由 OmniSharp 提供支持的 Visual Studio Code 扩展，并需要安装 [最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="90f9f-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
