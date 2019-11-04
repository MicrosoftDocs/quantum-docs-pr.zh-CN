---
title: 'Q # 技术-测试和调试 |Microsoft Docs'
description: 'Q # 技术-测试和调试'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183482"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="dee3a-103">测试和调试</span><span class="sxs-lookup"><span data-stu-id="dee3a-103">Testing and Debugging</span></span>

<span data-ttu-id="dee3a-104">与传统编程一样，必须能够检查量子程序是否按预期方式操作，并且能够诊断不正确的量程程序。</span><span class="sxs-lookup"><span data-stu-id="dee3a-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="dee3a-105">在本部分中，我们介绍了 Q # 提供的用于测试和调试量程程序的工具。</span><span class="sxs-lookup"><span data-stu-id="dee3a-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="dee3a-106">单元测试</span><span class="sxs-lookup"><span data-stu-id="dee3a-106">Unit Tests</span></span>

<span data-ttu-id="dee3a-107">测试传统程序的一种常见方法是编写称为*单元测试*的小程序，这些程序在库中运行代码，并将其输出与某个预期输出进行比较。</span><span class="sxs-lookup"><span data-stu-id="dee3a-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="dee3a-108">例如，我们可能需要确保 `Square(2)` 返回 `4`，因为我们知道 $ 2 ^ 2 = $4 的*先验*。</span><span class="sxs-lookup"><span data-stu-id="dee3a-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="dee3a-109">Q # 支持为量程程序创建单元测试，可在[xUnit](https://xunit.github.io/)单元测试框架中将其作为测试执行。</span><span class="sxs-lookup"><span data-stu-id="dee3a-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="dee3a-110">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="dee3a-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="dee3a-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="dee3a-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="dee3a-112">打开 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="dee3a-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="dee3a-113">请在 "`File`" 菜单中选择 "`New` > " `Project...`"。</span><span class="sxs-lookup"><span data-stu-id="dee3a-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="dee3a-114">在 "项目模板资源管理器" 中的 "`Installed` > `Visual C#`下，选择 `Q# Test Project` 模板。</span><span class="sxs-lookup"><span data-stu-id="dee3a-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="dee3a-115">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dee3a-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="dee3a-116">从你喜欢的命令行运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dee3a-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="dee3a-117">在任一情况下，新项目都将打开两个文件。</span><span class="sxs-lookup"><span data-stu-id="dee3a-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="dee3a-118">第一个文件 `Tests.qs`为定义新的 Q # 单元测试提供了一个方便的位置。</span><span class="sxs-lookup"><span data-stu-id="dee3a-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="dee3a-119">最初，此文件包含一个示例单元测试 `AllocateQubitTest`，它检查新分配的 qubit 是否在 $ \ket{0}$ 状态下并输出一条消息：</span><span class="sxs-lookup"><span data-stu-id="dee3a-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="dee3a-120">与类型 `(Unit => Unit)` 或与 `(Unit -> Unit)` 兼容的任何 Q # 操作都可以作为单元测试来执行。</span><span class="sxs-lookup"><span data-stu-id="dee3a-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="dee3a-121">第二个文件 `TestSuiteRunner.cs` 包含一个方法，该方法可发现并运行 Q # 单元测试。</span><span class="sxs-lookup"><span data-stu-id="dee3a-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="dee3a-122">这是 `TestTarget` 通过 `OperationDriver` 属性进行批注的方法。</span><span class="sxs-lookup"><span data-stu-id="dee3a-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="dee3a-123">`OperationDriver` 属性是 Xunit 扩展库 Xunit 中的一部分。</span><span class="sxs-lookup"><span data-stu-id="dee3a-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="dee3a-124">单元测试框架为它发现的每个 Q # 单元测试调用 `TestTarget` 方法。</span><span class="sxs-lookup"><span data-stu-id="dee3a-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="dee3a-125">框架通过 `op` 参数将单元测试说明传递给方法。</span><span class="sxs-lookup"><span data-stu-id="dee3a-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="dee3a-126">以下代码行：</span><span class="sxs-lookup"><span data-stu-id="dee3a-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="dee3a-127">对 `QuantumSimulator`执行单元测试。</span><span class="sxs-lookup"><span data-stu-id="dee3a-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="dee3a-128">默认情况下，单元测试发现机制将查找满足以下属性的所有 Q # 函数或兼容类型的操作：</span><span class="sxs-lookup"><span data-stu-id="dee3a-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="dee3a-129">与用 `OperationDriver` 特性批注的方法位于同一程序集中。</span><span class="sxs-lookup"><span data-stu-id="dee3a-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="dee3a-130">与用 `OperationDriver` 特性批注的方法位于同一命名空间中。</span><span class="sxs-lookup"><span data-stu-id="dee3a-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="dee3a-131">具有以 `Test`结尾的名称。</span><span class="sxs-lookup"><span data-stu-id="dee3a-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="dee3a-132">可以使用 `OperationDriver` 特性的可选参数设置程序集、命名空间以及单元测试函数和操作的后缀：</span><span class="sxs-lookup"><span data-stu-id="dee3a-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="dee3a-133">`AssemblyName` 参数设置要在其中搜索测试的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="dee3a-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="dee3a-134">`TestNamespace` 参数设置要在其中搜索测试的命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="dee3a-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="dee3a-135">`Suffix` 设置被视为单元测试的运算或函数名的后缀。</span><span class="sxs-lookup"><span data-stu-id="dee3a-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="dee3a-136">此外，`TestCasePrefix` 可选参数可用于设置测试用例的名称前缀。</span><span class="sxs-lookup"><span data-stu-id="dee3a-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="dee3a-137">操作名称前面的前缀将显示在测试用例的列表中。</span><span class="sxs-lookup"><span data-stu-id="dee3a-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="dee3a-138">例如，`TestCasePrefix = "QSim:"` 将导致 `AllocateQubitTest` 在找到的测试列表中显示为 "`QSim:AllocateQubitTest`"。</span><span class="sxs-lookup"><span data-stu-id="dee3a-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="dee3a-139">这对于指示用于运行测试的模拟器很有用。</span><span class="sxs-lookup"><span data-stu-id="dee3a-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="dee3a-140">运行 Q # 单元测试</span><span class="sxs-lookup"><span data-stu-id="dee3a-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="dee3a-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="dee3a-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="dee3a-142">作为一次性的每个解决方案设置，请前往 `Test` "菜单，并选择" `Test Settings` > `Default Processor Architecture` > `X64`"。</span><span class="sxs-lookup"><span data-stu-id="dee3a-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="dee3a-143">Visual Studio 的默认处理器结构设置存储在每个解决方案的解决方案选项（`.suo`）文件中。</span><span class="sxs-lookup"><span data-stu-id="dee3a-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="dee3a-144">如果删除此文件，则需要再次选择 "`X64`" 作为处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="dee3a-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="dee3a-145">生成项目，请在 "`Test`" 菜单中，选择 "`Windows` > " `Test Explorer`"。</span><span class="sxs-lookup"><span data-stu-id="dee3a-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="dee3a-146">`AllocateQubitTest` 将显示在 `Not Run Tests` 组中的测试列表中。</span><span class="sxs-lookup"><span data-stu-id="dee3a-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="dee3a-147">选择 `Run All` 或运行此单个测试，它应通过！</span><span class="sxs-lookup"><span data-stu-id="dee3a-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="dee3a-148">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dee3a-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="dee3a-149">若要运行测试，请导航到项目文件夹（包含 `Tests.csproj`的文件夹），然后执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dee3a-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="dee3a-150">应会看到类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="dee3a-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="dee3a-151">日志记录和断言</span><span class="sxs-lookup"><span data-stu-id="dee3a-151">Logging and Assertions</span></span>

<span data-ttu-id="dee3a-152">不会影响 Q # 中的函数的一项重要结果是，执行其输出类型为空元组的函数的任何影响将永远不会从 Q # 程序中观察到 `()`。</span><span class="sxs-lookup"><span data-stu-id="dee3a-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="dee3a-153">也就是说，目标计算机可以选择不执行任何返回 `()` 的函数，保证此省略不会修改任何以下 Q # 代码的行为。</span><span class="sxs-lookup"><span data-stu-id="dee3a-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="dee3a-154">这使函数返回 `()` 一个有用的工具，用于将断言和调试逻辑嵌入到 Q # 程序中。</span><span class="sxs-lookup"><span data-stu-id="dee3a-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="dee3a-155">日志记录</span><span class="sxs-lookup"><span data-stu-id="dee3a-155">Logging</span></span>

<span data-ttu-id="dee3a-156">内部函数 <xref:microsoft.quantum.intrinsic.message> 具有类型 `(String -> Unit)` 并支持创建诊断消息。</span><span class="sxs-lookup"><span data-stu-id="dee3a-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="dee3a-157">`QuantumSimulator` 的 `onLog` 操作可用于定义在 Q # 代码调用 `Message`时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="dee3a-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="dee3a-158">默认情况下，记录的消息将打印到标准输出。</span><span class="sxs-lookup"><span data-stu-id="dee3a-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="dee3a-159">定义单元测试套件时，可以将记录的消息定向到测试输出。</span><span class="sxs-lookup"><span data-stu-id="dee3a-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="dee3a-160">如果项目是通过 Q # 测试项目模板创建的，则会为该套件预先配置此重定向，并按如下所示创建默认值：</span><span class="sxs-lookup"><span data-stu-id="dee3a-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="dee3a-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="dee3a-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="dee3a-162">在测试资源管理器中执行测试并单击测试后，将显示一个面板，其中包含有关测试执行：已通过/失败状态、已用时间和 "输出" 链接的信息。</span><span class="sxs-lookup"><span data-stu-id="dee3a-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="dee3a-163">如果单击 "输出" 链接，则会在新窗口中打开 "测试输出"。</span><span class="sxs-lookup"><span data-stu-id="dee3a-163">If you click the "Output" link, test output will open in a new window.</span></span>

![测试输出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="dee3a-165">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dee3a-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="dee3a-166">通过 `dotnet test`将每个测试的通过/失败状态打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="dee3a-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="dee3a-167">对于未通过的测试，还会将上述 `output.WriteLine(msg)` 调用的输出记录到控制台中，以帮助诊断失败。</span><span class="sxs-lookup"><span data-stu-id="dee3a-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="dee3a-168">断言</span><span class="sxs-lookup"><span data-stu-id="dee3a-168">Assertions</span></span>

<span data-ttu-id="dee3a-169">可以应用相同的逻辑来实现断言。</span><span class="sxs-lookup"><span data-stu-id="dee3a-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="dee3a-170">我们来看一个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="dee3a-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="dee3a-171">此处，关键字 `fail` 指示不应继续计算，而是在运行 Q # 程序的目标计算机上引发异常。</span><span class="sxs-lookup"><span data-stu-id="dee3a-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="dee3a-172">按照定义，不能从 Q # 内观察到此类失败，因为在达到 `fail` 语句后，不会再运行 Q # 代码。</span><span class="sxs-lookup"><span data-stu-id="dee3a-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="dee3a-173">因此，如果我们继续执行对 `AssertPositive`的调用，则可以确保其输入为正值。</span><span class="sxs-lookup"><span data-stu-id="dee3a-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="dee3a-174">根据这些想法， [prelude](xref:microsoft.quantum.libraries.standard.prelude)提供两个特别有用的断言，<xref:microsoft.quantum.intrinsic.assert> 和 <xref:microsoft.quantum.intrinsic.assertprob> 建模为操作的 `()`。</span><span class="sxs-lookup"><span data-stu-id="dee3a-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="dee3a-175">这些断言每个都采用一个 Pauli 运算符，该运算符描述特定的感兴趣的度量、要对其执行度量的量程注册，以及一个假设结果。</span><span class="sxs-lookup"><span data-stu-id="dee3a-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="dee3a-176">在使用模拟的目标计算机上，我们不受非[克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的限制，并且可以在不干扰传递到此类断言的寄存器的情况下执行此类测量。</span><span class="sxs-lookup"><span data-stu-id="dee3a-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="dee3a-177">然后，模拟器可以类似于上面的 `AssertPositive` 函数，如果不在实践中观察到假设结果，则中止计算：</span><span class="sxs-lookup"><span data-stu-id="dee3a-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="dee3a-178">在物理量程硬件上，无克隆定理可防止对量程状态进行检查，`Assert` 和 `AssertProb` 操作只返回 `()`，不会产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="dee3a-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="dee3a-179"><xref:microsoft.quantum.diagnostics> 命名空间提供了 `Assert` 系列的更多功能，使我们可以检查更高级的条件。</span><span class="sxs-lookup"><span data-stu-id="dee3a-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="dee3a-180">转储函数</span><span class="sxs-lookup"><span data-stu-id="dee3a-180">Dump Functions</span></span>

<span data-ttu-id="dee3a-181">为了帮助解决量程程序问题，<xref:microsoft.quantum.diagnostics> 命名空间提供了两个函数，可将目标计算机的当前状态转储到文件： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister>。</span><span class="sxs-lookup"><span data-stu-id="dee3a-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="dee3a-182">每个生成的输出依赖于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="dee3a-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="dee3a-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="dee3a-183">DumpMachine</span></span>

<span data-ttu-id="dee3a-184">作为量程开发工具包的一部分分发的全状态量程模拟器会将整个量程系统的[声波函数](https://en.wikipedia.org/wiki/Wave_function)写入文件中，作为一维复数数组，其中每个元素都表示度量计算基础状态 $ \ket{n} $ 的概率，其中 $ \ket{n} = \ket{b_{n-1}.。。b_1b_0} $ 表示 bits $\{b_i\}$。</span><span class="sxs-lookup"><span data-stu-id="dee3a-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="dee3a-185">例如，在仅分配了两个 qubits 并在量程状态 $ $ \begin{align} \ket{\psi} = \frac 中的计算机上{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10}，\end{align} $ $ 调用 <xref:microsoft.quantum.diagnostics.dumpmachine> 生成此输出:</span><span class="sxs-lookup"><span data-stu-id="dee3a-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="dee3a-186">第一行提供了一个注释，其中包含相应 qubits 的 Id。</span><span class="sxs-lookup"><span data-stu-id="dee3a-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="dee3a-187">其余行说明了度量基准状态向量 $ \ket{n} $ 在笛卡尔和极坐标中的概率幅度。</span><span class="sxs-lookup"><span data-stu-id="dee3a-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="dee3a-188">对于第一行，详细信息：</span><span class="sxs-lookup"><span data-stu-id="dee3a-188">In detail for the first row:</span></span>

* <span data-ttu-id="dee3a-189">此行 **`∣0❭:`** 对应于 `0` 计算基础状态</span><span class="sxs-lookup"><span data-stu-id="dee3a-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="dee3a-190">**`0.707107 +  0.000000 i`** ：以笛卡尔格式的概率幅度。</span><span class="sxs-lookup"><span data-stu-id="dee3a-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="dee3a-191">**` == `** ： `equal` sign seperates 等效的表示形式。</span><span class="sxs-lookup"><span data-stu-id="dee3a-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="dee3a-192">**`**********  `** ：量的图形化表示形式，则 `*` 数与度量此状态向量的概率成正比。</span><span class="sxs-lookup"><span data-stu-id="dee3a-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="dee3a-193">**`[ 0.500000 ]`** ：量值的数值</span><span class="sxs-lookup"><span data-stu-id="dee3a-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="dee3a-194">**`    ---`** ：振幅阶段的图形化表示形式（见下文）。</span><span class="sxs-lookup"><span data-stu-id="dee3a-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="dee3a-195">**`[ 0.0000 rad ]`** ：阶段的数值（以弧度为单位）。</span><span class="sxs-lookup"><span data-stu-id="dee3a-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="dee3a-196">大小和阶段都以图形表示形式显示。</span><span class="sxs-lookup"><span data-stu-id="dee3a-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="dee3a-197">大小表示形式是一种直截了当的：它显示一条 `*`，这是条形图越大的概率。</span><span class="sxs-lookup"><span data-stu-id="dee3a-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="dee3a-198">对于阶段，我们将显示以下符号，以表示基于范围的角度：</span><span class="sxs-lookup"><span data-stu-id="dee3a-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="dee3a-199">下面的示例演示一些常见状态 `DumpMachine`：</span><span class="sxs-lookup"><span data-stu-id="dee3a-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="dee3a-200">Qubit 的 id 在运行时分配，不一定与 qubit 的分配顺序或其在 qubit 寄存器中的位置一致。</span><span class="sxs-lookup"><span data-stu-id="dee3a-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="dee3a-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="dee3a-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="dee3a-202">可以通过在代码中放置一个断点并检查 qubit 变量的值，来找出 Visual Studio 中的 qubit id，例如：</span><span class="sxs-lookup"><span data-stu-id="dee3a-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![在 Visual Studio 中显示 qubit id](~/media/qubit_id.png)
  >
  > <span data-ttu-id="dee3a-204">`register2` 的索引 `0` 的 qubit 具有 id =`3`，索引 `1` 为的 qubit 的 id 为`2`。</span><span class="sxs-lookup"><span data-stu-id="dee3a-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="dee3a-205">命令行/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dee3a-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="dee3a-206">可以通过使用 <xref:microsoft.quantum.intrinsic.message> 函数并在消息中传递 qubit 变量来找出 qubit id，例如：</span><span class="sxs-lookup"><span data-stu-id="dee3a-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="dee3a-207">这可能会生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="dee3a-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="dee3a-208">这意味着 `register2` 上索引 `0` 的 qubit 的 id =`3`，索引 `1` 的 qubit 的 id =`2`。</span><span class="sxs-lookup"><span data-stu-id="dee3a-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="dee3a-209"><xref:microsoft.quantum.diagnostics.dumpmachine> 是 <xref:microsoft.quantum.diagnostics> 命名空间的一部分，因此，若要使用它，必须添加 `open` 语句：</span><span class="sxs-lookup"><span data-stu-id="dee3a-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="dee3a-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="dee3a-210">DumpRegister</span></span>

<span data-ttu-id="dee3a-211"><xref:microsoft.quantum.diagnostics.dumpregister> 的工作方式类似于 <xref:microsoft.quantum.diagnostics.dumpmachine>，只不过它还采用 qubits 数组，以将信息量限制为仅与对应 qubits 相关。</span><span class="sxs-lookup"><span data-stu-id="dee3a-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="dee3a-212">与 <xref:microsoft.quantum.diagnostics.dumpmachine>一样，<xref:microsoft.quantum.diagnostics.dumpregister> 生成的信息取决于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="dee3a-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="dee3a-213">对于全状态量程模拟器，它会将波形函数写入文件中，由提供的 qubits 生成的量程子系统的全局阶段，格式与 <xref:microsoft.quantum.diagnostics.dumpmachine>相同。</span><span class="sxs-lookup"><span data-stu-id="dee3a-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="dee3a-214">例如，将只分配了两个 qubits 并在量程状态 $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10} =-e ^ {-i \ pi/4} \票证{0}-\frac{（1 + i）}{2} \ket{1}） \otimes \frac{-（1 + i）} {\sqrt{2}} \ket{0}），\end{align} $ $ 调用 <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` 生成此输出：</span><span class="sxs-lookup"><span data-stu-id="dee3a-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="dee3a-215">为 `qubit[1]` 调用 <xref:microsoft.quantum.diagnostics.dumpregister> 将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="dee3a-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="dee3a-216">通常，与另一寄存器放大的寄存器的状态为混合状态，而不是纯状态。</span><span class="sxs-lookup"><span data-stu-id="dee3a-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="dee3a-217">在这种情况下，<xref:microsoft.quantum.diagnostics.dumpregister> 输出以下消息：</span><span class="sxs-lookup"><span data-stu-id="dee3a-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="dee3a-218">下面的示例演示如何在 Q # 代码中使用 <xref:microsoft.quantum.diagnostics.dumpregister> 和 <xref:microsoft.quantum.diagnostics.dumpmachine>：</span><span class="sxs-lookup"><span data-stu-id="dee3a-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="dee3a-219">调试</span><span class="sxs-lookup"><span data-stu-id="dee3a-219">Debugging</span></span>

<span data-ttu-id="dee3a-220">在 `Assert` 和 `Dump` 函数和操作的基础上，Q # 支持标准 Visual Studio 调试功能的子集：[设置行断点](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[使用 F10 逐句通过代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)和[检查经典变量的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)在模拟器上的代码执行过程中可能会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="dee3a-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="dee3a-221">目前尚不支持在 Visual Studio Code 中进行调试。</span><span class="sxs-lookup"><span data-stu-id="dee3a-221">Debugging in Visual Studio Code is not yet supported.</span></span>

