---
title: 测试和调试
description: 了解如何使用单元测试、事实和断言以及转储函数来测试和调试量程程序。
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: dd6c7ae8a016423f26c37f3eedf0ae9c1d126b78
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630029"
---
# <a name="testing-and-debugging"></a>测试和调试

与传统编程一样，必须能够检查量子程序是否按预期方式操作，并且能够诊断不正确的量程程序。
在本部分中，我们介绍了 Q # 提供的用于测试和调试量程程序的工具。

## <a name="unit-tests"></a>单元测试

测试传统程序的一种常见方法是编写称为*单元测试*的小程序，这些程序在库中运行代码，并将其输出与某个预期输出进行比较。
例如，我们可能需要确保 `Square(2)` 返回 `4` ，因为我们知道 $ 2 ^ 2 = $4 的*先验*。

Q # 支持为量程程序创建单元测试，可在[xUnit](https://xunit.github.io/)单元测试框架中将其作为测试执行。

### <a name="creating-a-test-project"></a>创建测试项目

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

打开 Visual Studio 2019。 中转到 `File` 菜单并选择 `New`  >  `Project...` 。
在右上角搜索 `Q#` ，然后选择 `Q# Test Project` 模板。

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

从你喜欢的命令行运行以下命令：
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

你的新项目将具有一个文件 `Tests.qs` ，该文件提供了一个用于定义新的 Q # 单元测试的便利位置。
最初，此文件包含一个示例单元测试， `AllocateQubit` 该测试检查新分配的 qubit 是否处于 $ \ket {0} $ 状态并输出一条消息：

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

：新增：任何采用类型和返回参数的参数的 Q # 操作或函数 `Unit` `Unit` 都可以通过属性进行标记为单元测试 `@Test("...")` 。 此属性的参数（ `"QuantumSimulator"` 上面的）指定执行测试的目标。 可对多个目标执行单个测试。 例如，在上面添加一个 `@Test("ResourcesEstimator")` 属性 `AllocateQubit` 。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
保存该文件并执行所有测试。 现在应有两个单元测试，其中一个在 QuantumSimulator 上执行 AllocateQubit，另一个在 ResourceEstimator 中执行。 

Q # 编译器可识别内置目标 "QuantumSimulator"、"ToffoliSimulator" 和 "ResourcesEstimator" 作为单元测试的有效执行目标。 还可以指定任何完全限定名称来定义自定义执行目标。 

### <a name="running-q-unit-tests"></a>运行 Q # 单元测试

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

作为一次性的每个解决方案设置，请 `Test` 单击 "菜单" 并选择 `Test Settings`  >  `Default Processor Architecture`  >  `X64` 。

> [!TIP]
> Visual Studio 的默认处理器结构设置存储在每个解决方案的解决方案选项（ `.suo` ）文件中。
> 如果删除此文件，则需要 `X64` 再次选择作为处理器体系结构。

生成项目，请前往 `Test` 菜单并选择 `Windows`  >  `Test Explorer` 。 `AllocateQubit`将显示在组中的测试列表中 `Not Run Tests` 。 选择 `Run All` 或运行此单独的测试，应通过！

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

若要运行测试，请导航到项目文件夹（包含的文件夹 `Tests.csproj` ），然后执行以下命令：

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

可根据单元测试的名称和/或执行目标筛选单元测试：

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

内部函数 <xref:microsoft.quantum.intrinsic.message> 具有类型 `(String -> Unit)` ，并支持创建诊断消息。

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在测试资源管理器中执行测试并单击测试后，将显示一个面板，其中包含有关测试执行：已通过/失败状态、已用时间和 "输出" 链接的信息。 如果单击 "输出" 链接，则会在新窗口中打开 "测试输出"。

![测试输出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

每个测试的通过/失败状态将由打印到控制台 `dotnet test` 。
对于失败的测试，还会将输出输出到控制台，以帮助诊断故障。

***

## <a name="facts-and-assertions"></a>事实和断言

由于 Q # 中的函数没有任何_逻辑_副作用，因此，如果执行的函数的输出类型为空元组，则不能从 q # 程序内观察到该函数的任何_其他类型_的影响 `()` 。
也就是说，目标计算机可以选择不执行返回的任何函数，该函数 `()` 将不会修改任何以下 Q # 代码的行为。
这使函数返回 `()` （即 `Unit` ）一个有用的工具，用于将断言和调试逻辑嵌入到 Q # 程序中。 

我们来看一个简单的示例：

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

此处，关键字 `fail` 指示计算不应继续，而是在运行 Q # 程序的目标计算机上引发异常。
按照定义，不能从 Q # 内观察到此类故障，因为在到达语句后，不会再运行 Q # 代码 `fail` 。
这样，如果我们继续执行调用，就 `PositivityFact` 可以确保其输入是肯定的。

请注意，我们可以实现与 `PositivityFact` [`Fact`](xref:microsoft.quantum.diagnostics.fact) 从命名空间中使用函数相同的行为 <xref:microsoft.quantum.diagnostics> ：

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

另一方面，*断言*的使用方式类似于事实，但可能依赖于目标计算机的状态。 相应地，它们定义为操作，而事实定义为函数（如上所示）。
若要理解这一区别，请考虑在断言内使用以下事实：

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

在这里，我们将使用操作 <xref:microsoft.quantum.environment.getqubitsavailabletouse> 来返回可供使用的 qubits 数。
因为这显然依赖于程序及其执行环境的全局状态，所以，的定义 `AssertQubitsAreAvailable` 必须是一种操作。
但是，我们可以使用该全局状态生成简单 `Bool` 值作为函数的输入 `Fact` 。

根据这些想法， [prelude](xref:microsoft.quantum.libraries.standard.prelude)提供两个特别有用的断言， <xref:microsoft.quantum.intrinsic.assert> 并 <xref:microsoft.quantum.intrinsic.assertprob> 作为操作建模 `()` 。 这些断言每个都采用一个 Pauli 运算符，该运算符描述特定的感兴趣的度量、要对其执行度量的量程注册，以及一个假设结果。
在使用模拟的目标计算机上，我们不受非[克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的限制，并且可以在不干扰传递到此类断言的寄存器的情况下执行此类测量。
然后，模拟器可以类似于 `PositivityFact` 上述函数，如果不在实践中观察假设结果，则中止计算：

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

在物理量程硬件上，无克隆定理可防止对量程状态进行检查， `Assert` 且和 `AssertProb` 操作只返回， `()` 不会产生任何影响。

<xref:microsoft.quantum.diagnostics>命名空间提供了系列的更多功能， `Assert` 使我们能够查看更高级的条件。 

## <a name="dump-functions"></a>转储函数

为了帮助解决量程程序问题， <xref:microsoft.quantum.diagnostics> 命名空间提供了两个函数，可将目标计算机的当前状态转储到文件： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister> 。 每个生成的输出依赖于目标计算机。

### <a name="dumpmachine"></a>DumpMachine

作为量程开发工具包的一部分分发的全状态量程模拟器会将整个量程系统的[波形函数](https://en.wikipedia.org/wiki/Wave_function)写入文件中，这是一维复数数组，其中每个元素都表示度量计算基础状态 $ \ket{n} $ 的概率的波幅，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $ b_i $ b_1b_0} \{ $ \} 。 例如，在仅分配了两个 qubits 并在量程状态 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{（1 + i）} \ket 中的计算机上， {2} {10} \end{align} $ $ 调用将 <xref:microsoft.quantum.diagnostics.dumpmachine> 生成以下输出：

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一行提供了一个注释，其中包含相应 qubits 的 Id。
其余行说明了度量基准状态向量 $ \ket{n} $ 在笛卡尔和极坐标中的概率幅度。 对于第一行，详细信息：

* **`∣0❭:`** 该行与 `0` 计算基础状态相对应
* **`0.707107 +  0.000000 i`**：以笛卡尔格式的概率幅度。
* **` == `**： `equal` 符号分隔等效表示形式。
* **`**********  `**：大小的图形表示形式，的数量与 `*` 度量此状态向量的概率成正比。
* **`[ 0.500000 ]`**：量值的数值
* **`    ---`**：振幅阶段的图形化表示形式（见下文）。
* **`[ 0.0000 rad ]`**：阶段的数值（以弧度为单位）。

大小和阶段都以图形表示形式显示。 大小表示形式是一种直截了当的：它显示一个条形 `*` ，这越大越大。 对于阶段，我们将显示以下符号，以表示基于范围的角度：

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

以下示例演示 `DumpMachine` 了一些常见状态：

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


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > 可以通过在代码中放置一个断点并检查 qubit 变量的值，来找出 Visual Studio 中的 qubit id，例如：
  > 
  > ![在 Visual Studio 中显示 qubit id](~/media/qubit_id.png)
  >
  > 带有索引的 qubit `0` `register2` id =，具有 `3` 索引的 qubit 的 `1` id = `2` 。

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

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
  > 这意味着，具有索引的 qubit `0` `register2` id =，具有 `3` 索引的 qubit 的 `1` id = `2` 。


***

<xref:microsoft.quantum.diagnostics.dumpmachine>是 <xref:microsoft.quantum.diagnostics> 命名空间的一部分，因此，若要使用它，必须添加 `open` 语句：

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

<xref:microsoft.quantum.diagnostics.dumpregister>的工作方式类似 <xref:microsoft.quantum.diagnostics.dumpmachine> ，只不过它还采用 qubits 数组，以将信息量限制为仅与相应的 qubits 相关。

与一样 <xref:microsoft.quantum.diagnostics.dumpmachine> ，生成的信息 <xref:microsoft.quantum.diagnostics.dumpregister> 取决于目标计算机。 对于全状态量程模拟器，它会将波形功能写入文件，使其与所提供的 qubits 生成的量程子系统的全局阶段完全相同，格式与相同 <xref:microsoft.quantum.diagnostics.dumpmachine> 。  例如，再次使计算机只分配了两个 qubits，并在量程状态 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{（1 + i）} {2} \ket {10} =-e ^ {-i \ pi/4} （（\frac {1} {\sqrt} \ket-\frac{（1 + i）} {2} {0} {2} {1} {\ket {2} } \otimes {0} ），\end{align} $ $ 调用 <xref:microsoft.quantum.diagnostics.dumpregister> 来 `qubit[0]` 生成此输出：

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

和的调用将 <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[1]` 生成以下输出：

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

通常，与另一寄存器放大的寄存器的状态为混合状态，而不是纯状态。 在这种情况下，会 <xref:microsoft.quantum.diagnostics.dumpregister> 输出以下消息：

```
Qubits provided (0;) are entangled with some other qubit.
```

下面的示例演示如何 <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> 在 Q # 代码中使用和：

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

在 `Assert` 和 `Dump` 函数和操作的基础上，Q # 支持标准 Visual Studio 调试功能的子集：[设置行断点](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[使用 F10 逐句通过代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)和[检查典型变量的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)，在模拟器上的代码执行过程中可能会出现这种情况。

Visual Studio Code 中的调试利用了 c # 提供的调试功能作为由 OmniSharp 提供支持的 Visual Studio Code 扩展，并需要安装[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。 