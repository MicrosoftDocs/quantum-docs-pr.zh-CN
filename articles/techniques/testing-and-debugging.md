---
title: 测试和调试 Q# 程序
description: 了解如何使用单元测试、事实和断言以及转储函数来测试和调试量子程序。
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030576"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="f74ac-103">测试和调试</span><span class="sxs-lookup"><span data-stu-id="f74ac-103">Testing and Debugging</span></span>

<span data-ttu-id="f74ac-104">与经典编程一样，必须能够检查量子程序是否按预期操作，并能够诊断不正确的量子程序。</span><span class="sxs-lookup"><span data-stu-id="f74ac-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="f74ac-105">在本节中，我们将介绍 Q# 提供的用于测试和调试量子程序的工具。</span><span class="sxs-lookup"><span data-stu-id="f74ac-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="f74ac-106">单元测试</span><span class="sxs-lookup"><span data-stu-id="f74ac-106">Unit Tests</span></span>

<span data-ttu-id="f74ac-107">测试经典程序的一种常见方法是编写称为*单元测试*的小程序，这些程序在库中运行代码，并将其输出与一些预期输出进行比较。</span><span class="sxs-lookup"><span data-stu-id="f74ac-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="f74ac-108">例如，我们可能希望确保`Square(2)`返回`4`，因为我们知道*先验*的 $2⁄2 = 4$。</span><span class="sxs-lookup"><span data-stu-id="f74ac-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="f74ac-109">Q# 支持为量子程序创建单元测试，可在[xUnit](https://xunit.github.io/)单元测试框架中作为测试执行。</span><span class="sxs-lookup"><span data-stu-id="f74ac-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="f74ac-110">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="f74ac-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f74ac-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f74ac-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f74ac-112">打开 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="f74ac-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="f74ac-113">转到菜单并`File`选择`New` > `Project...`。</span><span class="sxs-lookup"><span data-stu-id="f74ac-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="f74ac-114">在右上角，搜索`Q#`，然后选择`Q# Test Project`模板。</span><span class="sxs-lookup"><span data-stu-id="f74ac-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f74ac-115">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f74ac-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f74ac-116">从您最喜爱的命令行中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f74ac-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="f74ac-117">您的新项目将有一个文件`Tests.qs`，这为定义新的 Q# 单元测试提供了一个方便的位置。</span><span class="sxs-lookup"><span data-stu-id="f74ac-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="f74ac-118">最初，此文件包含一个示例单元`AllocateQubit`测试，该测试检查新分配的 qubit 是否处于{0}$ket $ 状态并打印消息：</span><span class="sxs-lookup"><span data-stu-id="f74ac-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="f74ac-119">：new： 任何采用类型`Unit`和返回`Unit`参数的 Q# 操作或函数都可以通过`@Test("...")`属性标记为单元测试。</span><span class="sxs-lookup"><span data-stu-id="f74ac-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="f74ac-120">`"QuantumSimulator"`上面该属性的参数指定执行测试的目标。</span><span class="sxs-lookup"><span data-stu-id="f74ac-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="f74ac-121">可以在多个目标上执行单个测试。</span><span class="sxs-lookup"><span data-stu-id="f74ac-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="f74ac-122">例如，在 上`@Test("ResourcesEstimator")``AllocateQubit`添加一个属性。</span><span class="sxs-lookup"><span data-stu-id="f74ac-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="f74ac-123">保存文件并执行所有测试。</span><span class="sxs-lookup"><span data-stu-id="f74ac-123">Save the file and execute all tests.</span></span> <span data-ttu-id="f74ac-124">现在应该有两个单元测试，一个在昆腾模拟器上执行分配Qubit，另一个在资源估计器中执行。</span><span class="sxs-lookup"><span data-stu-id="f74ac-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="f74ac-125">Q# 编译器将内置目标"量子模拟器"、"Toffoli仿真器"和"资源估计器"识别为单元测试的有效执行目标。</span><span class="sxs-lookup"><span data-stu-id="f74ac-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="f74ac-126">还可以指定任何完全限定的名称来定义自定义执行目标。</span><span class="sxs-lookup"><span data-stu-id="f74ac-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="f74ac-127">运行 Q# 单元测试</span><span class="sxs-lookup"><span data-stu-id="f74ac-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f74ac-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f74ac-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f74ac-129">作为一次性`Test`每个解决方案设置，转到菜单并选择`Test Settings` > `Default Processor Architecture` > `X64`。</span><span class="sxs-lookup"><span data-stu-id="f74ac-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="f74ac-130">Visual Studio 的默认处理器体系结构设置存储在每个解决方案的解决方案选项`.suo`（ ） 文件中。</span><span class="sxs-lookup"><span data-stu-id="f74ac-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="f74ac-131">如果删除此文件，则需要再次选择`X64`作为处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="f74ac-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="f74ac-132">生成`Test`项目，转到菜单并选择`Windows` > `Test Explorer`。</span><span class="sxs-lookup"><span data-stu-id="f74ac-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="f74ac-133">`AllocateQubit`将显示在`Not Run Tests`组中的测试列表中。</span><span class="sxs-lookup"><span data-stu-id="f74ac-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="f74ac-134">选择`Run All`或运行此单个测试，并且它应该通过！</span><span class="sxs-lookup"><span data-stu-id="f74ac-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f74ac-135">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f74ac-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f74ac-136">要运行测试，请导航到项目文件夹（包含 的`Tests.csproj`文件夹），并执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f74ac-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="f74ac-137">应会看到类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="f74ac-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="f74ac-138">单元测试可以根据其名称和/或执行目标进行筛选：</span><span class="sxs-lookup"><span data-stu-id="f74ac-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="f74ac-139">内部函数<xref:microsoft.quantum.intrinsic.message>具有类型`(String -> Unit)`，并能够创建诊断消息。</span><span class="sxs-lookup"><span data-stu-id="f74ac-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f74ac-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f74ac-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f74ac-141">在测试资源管理器中执行测试并单击测试后，将显示一个面板，其中将显示有关测试执行的信息：通过/失败状态、已用时间和"输出"链接。</span><span class="sxs-lookup"><span data-stu-id="f74ac-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="f74ac-142">如果单击"输出"链接，测试输出将在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="f74ac-142">If you click the "Output" link, test output will open in a new window.</span></span>

![测试输出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f74ac-144">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f74ac-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f74ac-145">每个测试的通过/失败状态由`dotnet test`打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="f74ac-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="f74ac-146">对于失败的测试，输出也会打印到控制台，以帮助诊断故障。</span><span class="sxs-lookup"><span data-stu-id="f74ac-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="f74ac-147">事实与断言</span><span class="sxs-lookup"><span data-stu-id="f74ac-147">Facts and Assertions</span></span>

<span data-ttu-id="f74ac-148">由于 Q# 中的函数没有_逻辑_副作用，因此从 Q# 程序中永远无法观察到执行输出类型为空元组`()`的函数的任何其他_效果_。</span><span class="sxs-lookup"><span data-stu-id="f74ac-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="f74ac-149">也就是说，目标计算机可以选择不执行返回的任何函数`()`，保证此遗漏不会修改以下任何 Q# 代码的行为。</span><span class="sxs-lookup"><span data-stu-id="f74ac-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="f74ac-150">这使得函数返回`()`（即`Unit`） 成为将断言和调试逻辑嵌入到 Q# 程序中的有用工具。</span><span class="sxs-lookup"><span data-stu-id="f74ac-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="f74ac-151">让我们考虑一个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="f74ac-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="f74ac-152">此处，关键字`fail`指示计算不应继续，从而在运行 Q# 程序的目标计算机中引发异常。</span><span class="sxs-lookup"><span data-stu-id="f74ac-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="f74ac-153">根据定义，无法从 Q# 内部观察到此类故障，因为在到达语句后不会运行进一`fail`步的 Q# 代码。</span><span class="sxs-lookup"><span data-stu-id="f74ac-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="f74ac-154">因此，如果我们通过调用`PositivityFact`，我们可以放心，它的意见是积极的。</span><span class="sxs-lookup"><span data-stu-id="f74ac-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="f74ac-155">请注意，我们可以实现与`PositivityFact`使用[`Fact`](xref:microsoft.quantum.diagnostics.fact)<xref:microsoft.quantum.diagnostics>命名空间中的函数相同的行为：</span><span class="sxs-lookup"><span data-stu-id="f74ac-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="f74ac-156">另一方面，*断言*与事实类似，但可能取决于目标计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="f74ac-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="f74ac-157">相应地，它们定义为操作，而事实定义为函数（如上所述）。</span><span class="sxs-lookup"><span data-stu-id="f74ac-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="f74ac-158">要理解区别，请考虑以下在断言中使用事实：</span><span class="sxs-lookup"><span data-stu-id="f74ac-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="f74ac-159">在这里，我们使用 该操作<xref:microsoft.quantum.environment.getqubitsavailabletouse>返回可供使用的量子位数。</span><span class="sxs-lookup"><span data-stu-id="f74ac-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="f74ac-160">由于这显然取决于程序的全局状态及其执行环境，因此我们的定义`AssertQubitsAreAvailable`也必须是操作。</span><span class="sxs-lookup"><span data-stu-id="f74ac-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="f74ac-161">但是，我们可以使用该全局状态生成一个简单的`Bool`值作为函数的`Fact`输入。</span><span class="sxs-lookup"><span data-stu-id="f74ac-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="f74ac-162">在这些想法的基础上[，前奏](xref:microsoft.quantum.libraries.standard.prelude)提供了两个特别有用的断言，<xref:microsoft.quantum.intrinsic.assert>两<xref:microsoft.quantum.intrinsic.assertprob>者都模仿到`()`上的操作。</span><span class="sxs-lookup"><span data-stu-id="f74ac-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="f74ac-163">这些断言每个都采用一个 Pauli 运算符来描述特定的兴趣测量、要对其进行测量的量子寄存器以及假设结果。</span><span class="sxs-lookup"><span data-stu-id="f74ac-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="f74ac-164">在通过模拟工作的目标机器上，我们不受[无克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的约束，可以执行这种测量，而不会干扰传递给此类断言的寄存器。</span><span class="sxs-lookup"><span data-stu-id="f74ac-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="f74ac-165">然后，如果在实践中无法观察到假设结果`PositivityFact`，模拟器可以中止计算，类似于上面的函数：</span><span class="sxs-lookup"><span data-stu-id="f74ac-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="f74ac-166">在物理量子硬件上，无克隆定理阻止量子状态的检查，`Assert`和`AssertProb`操作只是返回`()`，没有其他效果。</span><span class="sxs-lookup"><span data-stu-id="f74ac-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="f74ac-167">命名<xref:microsoft.quantum.diagnostics>空间提供了`Assert`多个系列的函数，使我们能够检查更高级的条件。</span><span class="sxs-lookup"><span data-stu-id="f74ac-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="f74ac-168">转储函数</span><span class="sxs-lookup"><span data-stu-id="f74ac-168">Dump Functions</span></span>

<span data-ttu-id="f74ac-169">为了帮助对量子程序进行故障排除，<xref:microsoft.quantum.diagnostics>命名空间提供了两个函数，可以转储到文件中的目标计算机的当前状态：<xref:microsoft.quantum.diagnostics.dumpmachine>和<xref:microsoft.quantum.diagnostics.dumpregister>。</span><span class="sxs-lookup"><span data-stu-id="f74ac-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="f74ac-170">每个机器的生成输出取决于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="f74ac-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="f74ac-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="f74ac-171">DumpMachine</span></span>

<span data-ttu-id="f74ac-172">作为量子开发工具包的一部分分布的全态量子模拟器将整个量子系统的[波函数](https://en.wikipedia.org/wiki/Wave_function)写入文件，作为一维的复数数组，其中每个元素表示测量计算基础状态 $_ket_n$的概率的振幅，其中 $ket\n} = \ket\n= [ket\b_{n]...b_1b_0_$为位\{$b_i\}$。</span><span class="sxs-lookup"><span data-stu-id="f74ac-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="f74ac-173">例如，在只分配两个量子位且处于量子状态的计算机上，$$_开始\对齐_ket_psi}{1}= _frac [sqrt]{2}\ket{00} - [frac]（1 ={2} i）]\ket，[end]###$${10}调用<xref:microsoft.quantum.diagnostics.dumpmachine>将生成此输出：</span><span class="sxs-lookup"><span data-stu-id="f74ac-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f74ac-174">第一行按重要顺序提供具有相应量子位的的注释。</span><span class="sxs-lookup"><span data-stu-id="f74ac-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="f74ac-175">其余行描述以笛卡尔和极性格式测量基础状态向量 $_ket_n_$ 的概率振幅。</span><span class="sxs-lookup"><span data-stu-id="f74ac-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="f74ac-176">详细介绍第一行：</span><span class="sxs-lookup"><span data-stu-id="f74ac-176">In detail for the first row:</span></span>

* <span data-ttu-id="f74ac-177">**`∣0❭:`** 此行对应于`0`计算基础状态</span><span class="sxs-lookup"><span data-stu-id="f74ac-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="f74ac-178">**`0.707107 +  0.000000 i`**：以笛卡尔格式表示的概率振幅。</span><span class="sxs-lookup"><span data-stu-id="f74ac-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="f74ac-179">**` == `**：符号`equal`分离两个等效表示形式。</span><span class="sxs-lookup"><span data-stu-id="f74ac-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="f74ac-180">**`**********  `**： 震级的图形表示，数量`*`与测量此状态矢量的概率成正比。</span><span class="sxs-lookup"><span data-stu-id="f74ac-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="f74ac-181">**`[ 0.500000 ]`**：震级的数值</span><span class="sxs-lookup"><span data-stu-id="f74ac-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="f74ac-182">**`    ---`**： 振幅相的图形表示（见下文）。</span><span class="sxs-lookup"><span data-stu-id="f74ac-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="f74ac-183">**`[ 0.0000 rad ]`**：相位的数值（以弧度表示）。</span><span class="sxs-lookup"><span data-stu-id="f74ac-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="f74ac-184">大小和相位都显示图形表示。</span><span class="sxs-lookup"><span data-stu-id="f74ac-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="f74ac-185">幅度表示是直截了当的：它显示一个柱线`*`，柱值的概率越大。</span><span class="sxs-lookup"><span data-stu-id="f74ac-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="f74ac-186">对于相位，我们显示以下符号以表示基于范围的角度：</span><span class="sxs-lookup"><span data-stu-id="f74ac-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="f74ac-187">以下示例显示了`DumpMachine`某些常见状态：</span><span class="sxs-lookup"><span data-stu-id="f74ac-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="f74ac-188">qubit 的 ID 在运行时分配，它不一定与分配 qubit 的顺序或其在 qubit 寄存器中的位置保持一致。</span><span class="sxs-lookup"><span data-stu-id="f74ac-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f74ac-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f74ac-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="f74ac-190">您可以通过在代码中放置断点并检查 qubit 变量的值来在 Visual Studio 中找出 qubit ID，例如：</span><span class="sxs-lookup"><span data-stu-id="f74ac-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在视觉工作室中显示 qubit ID](~/media/qubit_id.png)
  >
  > <span data-ttu-id="f74ac-192">`0`索引上的`register2`qubit 具有 id=，`3`索引的 qubit`1`具有`2`id= 。</span><span class="sxs-lookup"><span data-stu-id="f74ac-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f74ac-193">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f74ac-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="f74ac-194">您可以通过使用<xref:microsoft.quantum.intrinsic.message>函数并传递消息中的 qubit 变量来找出 qubit ID，例如：</span><span class="sxs-lookup"><span data-stu-id="f74ac-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="f74ac-195">可以生成此输出：</span><span class="sxs-lookup"><span data-stu-id="f74ac-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="f74ac-196">这意味着`0``register2`索引上的 qubit 具有 id_，`3`索引的 qubit`1`具有 id=`2`。</span><span class="sxs-lookup"><span data-stu-id="f74ac-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="f74ac-197"><xref:microsoft.quantum.diagnostics.dumpmachine>是命名空间的<xref:microsoft.quantum.diagnostics>一部分，因此为了使用它，您必须添加一个`open`语句：</span><span class="sxs-lookup"><span data-stu-id="f74ac-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="f74ac-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="f74ac-198">DumpRegister</span></span>

<span data-ttu-id="f74ac-199"><xref:microsoft.quantum.diagnostics.dumpregister>工作方式<xref:microsoft.quantum.diagnostics.dumpmachine>如下，只不过还需要一个量子位数组来将信息量限制为仅与相应量子位相关的信息量。</span><span class="sxs-lookup"><span data-stu-id="f74ac-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="f74ac-200">与<xref:microsoft.quantum.diagnostics.dumpmachine>，生成<xref:microsoft.quantum.diagnostics.dumpregister>的信息取决于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="f74ac-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="f74ac-201">对于全态量子模拟器，它将波函数写入到量子子系统的全局阶段<xref:microsoft.quantum.diagnostics.dumpmachine>，该子系统由提供的量子位以与 的格式相同。</span><span class="sxs-lookup"><span data-stu-id="f74ac-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="f74ac-202">例如， 再次拍摄一台只分配两个量子位且处于量子状态的机器 $$开始 \ket_psi} = _frac{1}_sqrt{2}={00} ket - [frac[1 ={2} i]\ket{10} = - e_-i_pi/4{1}\* （{2}[frac{0} ]sqrt = \ket -{2} [frac]（1 ={1} i）] \ket） \fc_-（1 = i）][sqrt]{2}\ket），[{0}结束]\align= $$$$$s 调用<xref:microsoft.quantum.diagnostics.dumpregister>生成`qubit[0]`此输出：</span><span class="sxs-lookup"><span data-stu-id="f74ac-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f74ac-203">并调用<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[1]`生成此输出：</span><span class="sxs-lookup"><span data-stu-id="f74ac-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="f74ac-204">通常，与另一个寄存器纠缠的寄存器状态是混合状态，而不是纯状态。</span><span class="sxs-lookup"><span data-stu-id="f74ac-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="f74ac-205">在这种情况下，<xref:microsoft.quantum.diagnostics.dumpregister>输出以下消息：</span><span class="sxs-lookup"><span data-stu-id="f74ac-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="f74ac-206">下面的示例演示如何在 Q# 代码中使用<xref:microsoft.quantum.diagnostics.dumpregister>两<xref:microsoft.quantum.diagnostics.dumpmachine>者：</span><span class="sxs-lookup"><span data-stu-id="f74ac-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="f74ac-207">调试</span><span class="sxs-lookup"><span data-stu-id="f74ac-207">Debugging</span></span>

<span data-ttu-id="f74ac-208">除了函数和`Assert``Dump`操作，Q# 还支持标准 Visual Studio 调试功能的子集：在模拟器上的代码执行期间，可以使用 F10[设置线断点](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[单步执行代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)以及[检查经典变量的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)。</span><span class="sxs-lookup"><span data-stu-id="f74ac-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="f74ac-209">在 Visual Studio 代码中的调试利用了由 OmniSharp 提供支持的 Visual Studio 代码扩展 C# 提供的调试功能，并且需要安装[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。</span><span class="sxs-lookup"><span data-stu-id="f74ac-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
