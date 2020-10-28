---
title: 测试和调试
description: 了解如何使用单元测试、事实和断言以及转储函数来测试和调试量程程序。
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690962"
---
# <a name="testing-and-debugging"></a>测试和调试

与传统编程一样，必须能够检查量子程序是否按预期方式操作，并且能够诊断不正确的行为。
在本部分中，我们介绍了 Q# 用于测试和调试量程程序的工具。

## <a name="unit-tests"></a>单元测试

测试传统程序的一种常见方法是编写称为 *单元测试* 的小程序，这些程序在库中运行代码，并将其输出与某个预期输出进行比较。
例如，你可以确保返回， `Square(2)` `4` 因为你知道 $ 2 ^ 2 = $4 的 *先验* 。

Q# 支持为量程程序创建单元测试，并且该测试可以作为测试在 [xUnit](https://xunit.github.io/) 单元测试框架中运行。

### <a name="creating-a-test-project"></a>创建测试项目

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

打开 Visual Studio 2019。 请在 " **文件** " 菜单中选择 " **新建 > 项目 ...** "。在右上角，搜索 `Q#` ，然后选择 " **Q# 测试项目** " 模板。

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

从你喜欢的命令行运行以下命令：
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

你的新项目有一个文件 `Tests.qs` ，它提供了一个用于定义新单元测试的便利位置 Q# 。
最初，此文件包含一个示例单元测试， `AllocateQubit` 该测试检查新分配的 qubit 是否处于 $ \ket {0} $ 状态并输出一条消息：

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Q#采用类型为的参数和返回的任何操作或函数 `Unit` `Unit` 都可以通过属性标记为单元测试 `@Test("...")` 。 在上面的示例中，该属性的参数（ `"QuantumSimulator"` ）指定测试运行的目标。 单个测试可以在多个目标上运行。 例如，在之前添加一个 `@Test("ResourcesEstimator")` 属性 `AllocateQubit` 。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
保存该文件并运行所有测试。 现在应有两个单元测试，一个在 `AllocateQubit` 上运行，另一个 `QuantumSimulator` 在上运行 `ResourcesEstimator` 。 

Q#编译器可识别内置目标 `"QuantumSimulator"` 、 `"ToffoliSimulator"` 和， `"ResourcesEstimator"` 作为单元测试的有效运行目标。 还可以指定任何完全限定的名称来定义自定义的运行目标。 

### <a name="running-no-locq-unit-tests"></a>运行 Q# 单元测试

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

作为一次性的每个解决方案设置，请在 " **测试** " 菜单中，选择 " **测试设置" > 默认处理器体系结构 > X64** 。

> [!TIP]
> Visual Studio 的默认处理器结构设置存储在解决方案选项 (`.suo` 每个解决方案) 文件中。
> 如果删除此文件，则需要再次选择 **X64** 作为处理器体系结构。

生成项目，打开 " **测试** " 菜单，然后选择 " **Windows > 测试资源管理器** "。 **AllocateQubit** 在 " **未运行的测试** " 组中的测试列表中显示。 选择 " **全部运行** " 或 "运行此单个测试"。

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

若要运行测试，请导航到包含) 的文件夹 (项目文件夹 `Tests.csproj` ，并运行以下命令：

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

可以根据其名称或运行目标筛选单元测试：

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


**_

内部函数 <xref:Microsoft.Quantum.Intrinsic.Message> 具有类型 `(String -> Unit)` ，并支持创建诊断消息。

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在测试资源管理器中运行测试并单击测试后，将显示一个面板，其中包含有关测试运行的信息：通过/失败状态、运行时间和输出链接。 单击 "_ *输出* *" 可在新窗口中打开测试输出。

![测试输出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

每个测试的通过/失败状态将由打印到控制台 `dotnet test` 。
对于失败的测试，还会将输出输出到控制台，以帮助诊断故障。

**_

## <a name="facts-and-assertions"></a>事实和断言

因为中的函数没有 Q# 任何 _逻辑_ 副作用，所以，你永远不会观察到 Q# 程序中的任何其他类型的效果，因为它运行的函数的输出类型为空元组 `()` 。
也就是说，目标计算机可以选择不运行返回的任何函数， `()` 保证此省略不会修改任何以下代码的行为 Q# 。
此行为使函数返回 `()` (如 `Unit`) 用于将断言和调试逻辑嵌入到程序中的有用工具 Q# 。 

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

此处，关键字 `fail` 指示计算不应继续，并在运行程序的目标计算机上引发异常 Q# 。
按照定义，无法从内观察到此类故障 Q# ，因为目标计算机在 Q# 到达语句后不再运行代码 `fail` 。
因此，如果我们继续通过调用，则 `PositivityFact` 可以确保其输入为正值。

请注意，我们可以实现与 `PositivityFact` [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) 从命名空间中使用函数相同的行为 <xref:Microsoft.Quantum.Diagnostics> ：

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

另一方面，_Assertions * 与事实类似，但可能依赖于目标计算机的状态。 它们相应地定义为操作，而事实定义为函数 (如前面的示例) 中所示。
若要理解这一区别，请考虑在断言内使用以下事实：

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

在这里，我们将使用操作 <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> 来返回可供使用的 qubits 数。
因为这取决于程序及其运行环境的全局状态，所以，的定义 `AssertQubitsAreAvailable` 必须也是操作。
但是，我们可以使用该全局状态生成简单 `Bool` 值作为函数的输入 `Fact` 。

基于这些观点构建[的 prelude](xref:microsoft.quantum.libraries.standard.prelude)提供两个特别有用的断言， <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 并 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 作为操作建模 `()` 。 这些断言每个都采用一个 Pauli 运算符，该运算符描述特定的感兴趣的度量、在其上执行度量的量程注册，以及一个假设结果。
模拟使用的目标计算机不受非 [克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的约束，并且可以在不干扰传递到此类断言的寄存器的情况下执行此类测量。
然后，模拟器可以类似于 `PositivityFact` previous 函数，如果在实践中未发现假设结果，则停止计算：

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

在物理量程硬件上，非克隆定理阻止对量程状态的检查， `AssertMeasurement` 且和 `AssertMeasurementProbability` 操作只返回， `()` 不会产生任何影响。

<xref:Microsoft.Quantum.Diagnostics>命名空间提供了更多系列功能 `Assert` ，您可以在其中查看更高级的条件。 

## <a name="dump-functions"></a>转储函数

为了帮助解决量程程序问题， <xref:Microsoft.Quantum.Diagnostics> 命名空间提供了两个函数，可将目标计算机的当前状态转储到文件： <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 和 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 。 每个生成的输出依赖于目标计算机。

### <a name="dumpmachine"></a>DumpMachine

作为量程开发工具包的一部分分发的全状态量程模拟器会将整个量程系统的 [波形函数](https://en.wikipedia.org/wiki/Wave_function) 写入文件中，这是一维复数数组，其中每个元素都表示度量计算基础状态 $ \ket{n} $ 的概率的波幅，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $ b_i $ b_1b_0} \{ $ \} 。 例如，在仅分配了两个 qubits 并在量程状态 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } \ket 中的计算机上 {2} {10} ，\end{align} $ $ 调用将 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 生成以下输出：

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一行提供了一个注释，其中包含相应 qubits 的 id。
其余行说明了度量基准状态向量 $ \ket{n} $ 在笛卡尔和极坐标中的概率幅度。 对于第一行，详细信息：

* **`∣0❭:`** 该行与 `0` 计算基础状态相对应
* **`0.707107 +  0.000000 i`** ：以笛卡尔格式的概率幅度。
* **` == `** ： `equal` 符号分隔等效表示形式。
* **`**********  `** ：大小的图形表示形式，的数量与 `*` 度量此状态向量的概率成正比。
* **`[ 0.500000 ]`** ：量值的数值
* **`    ---`** ：振幅阶段的图形表示形式 (参阅以下输出) 。
* **`[ 0.0000 rad ]`** ：相位 (的数值) 以弧度表示。

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
  > 可以通过在代码中放置一个断点并检查 qubit 变量的值，在 Visual Studio 中查找 qubit id，例如：
  > 
  > ![在 Visual Studio 中显示 qubit id](~/media/qubit_id.png)
  >
  > 带有索引的 qubit `0` `register2` id =，具有 `3` 索引的 qubit 的 `1` id = `2` 。

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 您可以使用函数查找 qubit id， <xref:Microsoft.Quantum.Intrinsic.Message> 并在消息中传递 qubit 变量，例如：
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


**_

由于 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 是  <xref:Microsoft.Quantum.Diagnostics> 命名空间的一部分，因此必须添加 `open` 语句来访问它：

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

<xref:Microsoft.Quantum.Diagnostics.DumpRegister> 的工作方式类似 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ，不同之处在于它还采用 qubits 数组，以将信息量限制为仅与对应 qubits 相关。

与一样 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ，生成的信息 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 取决于目标计算机。 对于全状态量程模拟器，它会将波形功能写入文件，使其与所提供的 qubits 生成的量程子系统的全局阶段完全相同，格式与相同 <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 。  例如，再次使计算机只分配了两个 qubits，并在量程状态 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } {2} \ket {10} =-e ^ {-i \ pi/4} ( ( \frac {1} {\sqrt {2} } \ket {0} -\frac{ (1 + i) {2} } \ket {1} ) \otimes \frac{- ({2} {0} \end{align} $ $ 调用 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 来 `qubit[0]` 生成此输出：

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

和的调用将 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> `qubit[1]` 生成以下输出：

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

通常，与另一寄存器放大的寄存器的状态为混合状态，而不是纯状态。 在这种情况下，会 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 输出以下消息：

```
Qubits provided (0;) are entangled with some other qubit.
```

下面的示例演示如何 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 在代码中使用和 Q# ：

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

在 `Assert` 和 `Dump` 函数和操作的基础上， Q# 支持标准 Visual Studio 调试功能的子集： [设置行断点](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [使用 F10 逐句通过代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)，以及在模拟器上运行代码时，可以 [检查经典变量的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) 。

Visual Studio Code 中的调试利用了 c # 提供的调试功能作为由 OmniSharp 提供支持的 Visual Studio Code 扩展，并需要安装 [最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。 
