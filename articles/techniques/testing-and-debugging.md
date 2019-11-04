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
# <a name="testing-and-debugging"></a>测试和调试

与传统编程一样，必须能够检查量子程序是否按预期方式操作，并且能够诊断不正确的量程程序。
在本部分中，我们介绍了 Q # 提供的用于测试和调试量程程序的工具。

## <a name="unit-tests"></a>单元测试

测试传统程序的一种常见方法是编写称为*单元测试*的小程序，这些程序在库中运行代码，并将其输出与某个预期输出进行比较。
例如，我们可能需要确保 `Square(2)` 返回 `4`，因为我们知道 $ 2 ^ 2 = $4 的*先验*。

Q # 支持为量程程序创建单元测试，可在[xUnit](https://xunit.github.io/)单元测试框架中将其作为测试执行。

### <a name="creating-a-test-project"></a>创建测试项目

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

打开 Visual Studio 2019。 请在 "`File`" 菜单中选择 "`New` > " `Project...`"。
在 "项目模板资源管理器" 中的 "`Installed` > `Visual C#`下，选择 `Q# Test Project` 模板。

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

从你喜欢的命令行运行以下命令：
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

在任一情况下，新项目都将打开两个文件。
第一个文件 `Tests.qs`为定义新的 Q # 单元测试提供了一个方便的位置。
最初，此文件包含一个示例单元测试 `AllocateQubitTest`，它检查新分配的 qubit 是否在 $ \ket{0}$ 状态下并输出一条消息：

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

与类型 `(Unit => Unit)` 或与 `(Unit -> Unit)` 兼容的任何 Q # 操作都可以作为单元测试来执行。 

第二个文件 `TestSuiteRunner.cs` 包含一个方法，该方法可发现并运行 Q # 单元测试。 这是 `TestTarget` 通过 `OperationDriver` 属性进行批注的方法。
`OperationDriver` 属性是 Xunit 扩展库 Xunit 中的一部分。
单元测试框架为它发现的每个 Q # 单元测试调用 `TestTarget` 方法。
框架通过 `op` 参数将单元测试说明传递给方法。 以下代码行：
```csharp
op.TestOperationRunner(sim);
```
对 `QuantumSimulator`执行单元测试。

默认情况下，单元测试发现机制将查找满足以下属性的所有 Q # 函数或兼容类型的操作：
* 与用 `OperationDriver` 特性批注的方法位于同一程序集中。
* 与用 `OperationDriver` 特性批注的方法位于同一命名空间中。
* 具有以 `Test`结尾的名称。

可以使用 `OperationDriver` 特性的可选参数设置程序集、命名空间以及单元测试函数和操作的后缀：
* `AssemblyName` 参数设置要在其中搜索测试的程序集的名称。
* `TestNamespace` 参数设置要在其中搜索测试的命名空间的名称。
* `Suffix` 设置被视为单元测试的运算或函数名的后缀。

此外，`TestCasePrefix` 可选参数可用于设置测试用例的名称前缀。 操作名称前面的前缀将显示在测试用例的列表中。 例如，`TestCasePrefix = "QSim:"` 将导致 `AllocateQubitTest` 在找到的测试列表中显示为 "`QSim:AllocateQubitTest`"。 这对于指示用于运行测试的模拟器很有用。

### <a name="running-q-unit-tests"></a>运行 Q # 单元测试

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

作为一次性的每个解决方案设置，请前往 `Test` "菜单，并选择" `Test Settings` > `Default Processor Architecture` > `X64`"。

> [!TIP]
> Visual Studio 的默认处理器结构设置存储在每个解决方案的解决方案选项（`.suo`）文件中。
> 如果删除此文件，则需要再次选择 "`X64`" 作为处理器体系结构。

生成项目，请在 "`Test`" 菜单中，选择 "`Windows` > " `Test Explorer`"。 `AllocateQubitTest` 将显示在 `Not Run Tests` 组中的测试列表中。 选择 `Run All` 或运行此单个测试，它应通过！

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

若要运行测试，请导航到项目文件夹（包含 `Tests.csproj`的文件夹），然后执行以下命令：

```bash
$ dotnet restore
$ dotnet test
```

应会看到类似于下面的输出：

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

## <a name="logging-and-assertions"></a>日志记录和断言

不会影响 Q # 中的函数的一项重要结果是，执行其输出类型为空元组的函数的任何影响将永远不会从 Q # 程序中观察到 `()`。
也就是说，目标计算机可以选择不执行任何返回 `()` 的函数，保证此省略不会修改任何以下 Q # 代码的行为。
这使函数返回 `()` 一个有用的工具，用于将断言和调试逻辑嵌入到 Q # 程序中。 

### <a name="logging"></a>日志记录

内部函数 <xref:microsoft.quantum.intrinsic.message> 具有类型 `(String -> Unit)` 并支持创建诊断消息。

`QuantumSimulator` 的 `onLog` 操作可用于定义在 Q # 代码调用 `Message`时执行的操作。 默认情况下，记录的消息将打印到标准输出。

定义单元测试套件时，可以将记录的消息定向到测试输出。 如果项目是通过 Q # 测试项目模板创建的，则会为该套件预先配置此重定向，并按如下所示创建默认值：

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在测试资源管理器中执行测试并单击测试后，将显示一个面板，其中包含有关测试执行：已通过/失败状态、已用时间和 "输出" 链接的信息。 如果单击 "输出" 链接，则会在新窗口中打开 "测试输出"。

![测试输出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

通过 `dotnet test`将每个测试的通过/失败状态打印到控制台。
对于未通过的测试，还会将上述 `output.WriteLine(msg)` 调用的输出记录到控制台中，以帮助诊断失败。

***

### <a name="assertions"></a>断言

可以应用相同的逻辑来实现断言。 我们来看一个简单的示例：

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

此处，关键字 `fail` 指示不应继续计算，而是在运行 Q # 程序的目标计算机上引发异常。
按照定义，不能从 Q # 内观察到此类失败，因为在达到 `fail` 语句后，不会再运行 Q # 代码。
因此，如果我们继续执行对 `AssertPositive`的调用，则可以确保其输入为正值。

根据这些想法， [prelude](xref:microsoft.quantum.libraries.standard.prelude)提供两个特别有用的断言，<xref:microsoft.quantum.intrinsic.assert> 和 <xref:microsoft.quantum.intrinsic.assertprob> 建模为操作的 `()`。 这些断言每个都采用一个 Pauli 运算符，该运算符描述特定的感兴趣的度量、要对其执行度量的量程注册，以及一个假设结果。
在使用模拟的目标计算机上，我们不受非[克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的限制，并且可以在不干扰传递到此类断言的寄存器的情况下执行此类测量。
然后，模拟器可以类似于上面的 `AssertPositive` 函数，如果不在实践中观察到假设结果，则中止计算：

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

在物理量程硬件上，无克隆定理可防止对量程状态进行检查，`Assert` 和 `AssertProb` 操作只返回 `()`，不会产生任何影响。

<xref:microsoft.quantum.diagnostics> 命名空间提供了 `Assert` 系列的更多功能，使我们可以检查更高级的条件。 

## <a name="dump-functions"></a>转储函数

为了帮助解决量程程序问题，<xref:microsoft.quantum.diagnostics> 命名空间提供了两个函数，可将目标计算机的当前状态转储到文件： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister>。 每个生成的输出依赖于目标计算机。

### <a name="dumpmachine"></a>DumpMachine

作为量程开发工具包的一部分分发的全状态量程模拟器会将整个量程系统的[声波函数](https://en.wikipedia.org/wiki/Wave_function)写入文件中，作为一维复数数组，其中每个元素都表示度量计算基础状态 $ \ket{n} $ 的概率，其中 $ \ket{n} = \ket{b_{n-1}.。。b_1b_0} $ 表示 bits $\{b_i\}$。 例如，在仅分配了两个 qubits 并在量程状态 $ $ \begin{align} \ket{\psi} = \frac 中的计算机上{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10}，\end{align} $ $ 调用 <xref:microsoft.quantum.diagnostics.dumpmachine> 生成此输出:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一行提供了一个注释，其中包含相应 qubits 的 Id。
其余行说明了度量基准状态向量 $ \ket{n} $ 在笛卡尔和极坐标中的概率幅度。 对于第一行，详细信息：

* 此行 **`∣0❭:`** 对应于 `0` 计算基础状态
* **`0.707107 +  0.000000 i`** ：以笛卡尔格式的概率幅度。
* **` == `** ： `equal` sign seperates 等效的表示形式。
* **`**********  `** ：量的图形化表示形式，则 `*` 数与度量此状态向量的概率成正比。
* **`[ 0.500000 ]`** ：量值的数值
* **`    ---`** ：振幅阶段的图形化表示形式（见下文）。
* **`[ 0.0000 rad ]`** ：阶段的数值（以弧度为单位）。

大小和阶段都以图形表示形式显示。 大小表示形式是一种直截了当的：它显示一条 `*`，这是条形图越大的概率。 对于阶段，我们将显示以下符号，以表示基于范围的角度：

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

下面的示例演示一些常见状态 `DumpMachine`：

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
  > Qubit 的 id 在运行时分配，不一定与 qubit 的分配顺序或其在 qubit 寄存器中的位置一致。


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > 可以通过在代码中放置一个断点并检查 qubit 变量的值，来找出 Visual Studio 中的 qubit id，例如：
  > 
  > ![在 Visual Studio 中显示 qubit id](~/media/qubit_id.png)
  >
  > `register2` 的索引 `0` 的 qubit 具有 id =`3`，索引 `1` 为的 qubit 的 id 为`2`。

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 可以通过使用 <xref:microsoft.quantum.intrinsic.message> 函数并在消息中传递 qubit 变量来找出 qubit id，例如：
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 这可能会生成以下输出：
  >```
  > 0=q:3; 1=q:2
  >```
  > 这意味着 `register2` 上索引 `0` 的 qubit 的 id =`3`，索引 `1` 的 qubit 的 id =`2`。


***

<xref:microsoft.quantum.diagnostics.dumpmachine> 是 <xref:microsoft.quantum.diagnostics> 命名空间的一部分，因此，若要使用它，必须添加 `open` 语句：

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


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister> 的工作方式类似于 <xref:microsoft.quantum.diagnostics.dumpmachine>，只不过它还采用 qubits 数组，以将信息量限制为仅与对应 qubits 相关。

与 <xref:microsoft.quantum.diagnostics.dumpmachine>一样，<xref:microsoft.quantum.diagnostics.dumpregister> 生成的信息取决于目标计算机。 对于全状态量程模拟器，它会将波形函数写入文件中，由提供的 qubits 生成的量程子系统的全局阶段，格式与 <xref:microsoft.quantum.diagnostics.dumpmachine>相同。  例如，将只分配了两个 qubits 并在量程状态 $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10} =-e ^ {-i \ pi/4} \票证{0}-\frac{（1 + i）}{2} \ket{1}） \otimes \frac{-（1 + i）} {\sqrt{2}} \ket{0}），\end{align} $ $ 调用 <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` 生成此输出：

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

为 `qubit[1]` 调用 <xref:microsoft.quantum.diagnostics.dumpregister> 将生成以下输出：

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

通常，与另一寄存器放大的寄存器的状态为混合状态，而不是纯状态。 在这种情况下，<xref:microsoft.quantum.diagnostics.dumpregister> 输出以下消息：

```
Qubits provided (0;) are entangled with some other qubit.
```

下面的示例演示如何在 Q # 代码中使用 <xref:microsoft.quantum.diagnostics.dumpregister> 和 <xref:microsoft.quantum.diagnostics.dumpmachine>：

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

## <a name="debugging"></a>调试

在 `Assert` 和 `Dump` 函数和操作的基础上，Q # 支持标准 Visual Studio 调试功能的子集：[设置行断点](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[使用 F10 逐句通过代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)和[检查经典变量的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)在模拟器上的代码执行过程中可能会出现这种情况。

目前尚不支持在 Visual Studio Code 中进行调试。

