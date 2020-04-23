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
# <a name="testing-and-debugging"></a>测试和调试

与经典编程一样，必须能够检查量子程序是否按预期操作，并能够诊断不正确的量子程序。
在本节中，我们将介绍 Q# 提供的用于测试和调试量子程序的工具。

## <a name="unit-tests"></a>单元测试

测试经典程序的一种常见方法是编写称为*单元测试*的小程序，这些程序在库中运行代码，并将其输出与一些预期输出进行比较。
例如，我们可能希望确保`Square(2)`返回`4`，因为我们知道*先验*的 $2⁄2 = 4$。

Q# 支持为量子程序创建单元测试，可在[xUnit](https://xunit.github.io/)单元测试框架中作为测试执行。

### <a name="creating-a-test-project"></a>创建测试项目

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

打开 Visual Studio 2019。 转到菜单并`File`选择`New` > `Project...`。
在右上角，搜索`Q#`，然后选择`Q# Test Project`模板。

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

从您最喜爱的命令行中，运行以下命令：
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

您的新项目将有一个文件`Tests.qs`，这为定义新的 Q# 单元测试提供了一个方便的位置。
最初，此文件包含一个示例单元`AllocateQubit`测试，该测试检查新分配的 qubit 是否处于{0}$ket $ 状态并打印消息：

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

：new： 任何采用类型`Unit`和返回`Unit`参数的 Q# 操作或函数都可以通过`@Test("...")`属性标记为单元测试。 `"QuantumSimulator"`上面该属性的参数指定执行测试的目标。 可以在多个目标上执行单个测试。 例如，在 上`@Test("ResourcesEstimator")``AllocateQubit`添加一个属性。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
保存文件并执行所有测试。 现在应该有两个单元测试，一个在昆腾模拟器上执行分配Qubit，另一个在资源估计器中执行。 

Q# 编译器将内置目标"量子模拟器"、"Toffoli仿真器"和"资源估计器"识别为单元测试的有效执行目标。 还可以指定任何完全限定的名称来定义自定义执行目标。 

### <a name="running-q-unit-tests"></a>运行 Q# 单元测试

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

作为一次性`Test`每个解决方案设置，转到菜单并选择`Test Settings` > `Default Processor Architecture` > `X64`。

> [!TIP]
> Visual Studio 的默认处理器体系结构设置存储在每个解决方案的解决方案选项`.suo`（ ） 文件中。
> 如果删除此文件，则需要再次选择`X64`作为处理器体系结构。

生成`Test`项目，转到菜单并选择`Windows` > `Test Explorer`。 `AllocateQubit`将显示在`Not Run Tests`组中的测试列表中。 选择`Run All`或运行此单个测试，并且它应该通过！

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

要运行测试，请导航到项目文件夹（包含 的`Tests.csproj`文件夹），并执行以下命令：

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

单元测试可以根据其名称和/或执行目标进行筛选：

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

内部函数<xref:microsoft.quantum.intrinsic.message>具有类型`(String -> Unit)`，并能够创建诊断消息。

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在测试资源管理器中执行测试并单击测试后，将显示一个面板，其中将显示有关测试执行的信息：通过/失败状态、已用时间和"输出"链接。 如果单击"输出"链接，测试输出将在新窗口中打开。

![测试输出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

每个测试的通过/失败状态由`dotnet test`打印到控制台。
对于失败的测试，输出也会打印到控制台，以帮助诊断故障。

***

## <a name="facts-and-assertions"></a>事实与断言

由于 Q# 中的函数没有_逻辑_副作用，因此从 Q# 程序中永远无法观察到执行输出类型为空元组`()`的函数的任何其他_效果_。
也就是说，目标计算机可以选择不执行返回的任何函数`()`，保证此遗漏不会修改以下任何 Q# 代码的行为。
这使得函数返回`()`（即`Unit`） 成为将断言和调试逻辑嵌入到 Q# 程序中的有用工具。 

让我们考虑一个简单的示例：

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

此处，关键字`fail`指示计算不应继续，从而在运行 Q# 程序的目标计算机中引发异常。
根据定义，无法从 Q# 内部观察到此类故障，因为在到达语句后不会运行进一`fail`步的 Q# 代码。
因此，如果我们通过调用`PositivityFact`，我们可以放心，它的意见是积极的。

请注意，我们可以实现与`PositivityFact`使用[`Fact`](xref:microsoft.quantum.diagnostics.fact)<xref:microsoft.quantum.diagnostics>命名空间中的函数相同的行为：

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

另一方面，*断言*与事实类似，但可能取决于目标计算机的状态。 相应地，它们定义为操作，而事实定义为函数（如上所述）。
要理解区别，请考虑以下在断言中使用事实：

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

在这里，我们使用 该操作<xref:microsoft.quantum.environment.getqubitsavailabletouse>返回可供使用的量子位数。
由于这显然取决于程序的全局状态及其执行环境，因此我们的定义`AssertQubitsAreAvailable`也必须是操作。
但是，我们可以使用该全局状态生成一个简单的`Bool`值作为函数的`Fact`输入。

在这些想法的基础上[，前奏](xref:microsoft.quantum.libraries.standard.prelude)提供了两个特别有用的断言，<xref:microsoft.quantum.intrinsic.assert>两<xref:microsoft.quantum.intrinsic.assertprob>者都模仿到`()`上的操作。 这些断言每个都采用一个 Pauli 运算符来描述特定的兴趣测量、要对其进行测量的量子寄存器以及假设结果。
在通过模拟工作的目标机器上，我们不受[无克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的约束，可以执行这种测量，而不会干扰传递给此类断言的寄存器。
然后，如果在实践中无法观察到假设结果`PositivityFact`，模拟器可以中止计算，类似于上面的函数：

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

在物理量子硬件上，无克隆定理阻止量子状态的检查，`Assert`和`AssertProb`操作只是返回`()`，没有其他效果。

命名<xref:microsoft.quantum.diagnostics>空间提供了`Assert`多个系列的函数，使我们能够检查更高级的条件。 

## <a name="dump-functions"></a>转储函数

为了帮助对量子程序进行故障排除，<xref:microsoft.quantum.diagnostics>命名空间提供了两个函数，可以转储到文件中的目标计算机的当前状态：<xref:microsoft.quantum.diagnostics.dumpmachine>和<xref:microsoft.quantum.diagnostics.dumpregister>。 每个机器的生成输出取决于目标计算机。

### <a name="dumpmachine"></a>DumpMachine

作为量子开发工具包的一部分分布的全态量子模拟器将整个量子系统的[波函数](https://en.wikipedia.org/wiki/Wave_function)写入文件，作为一维的复数数组，其中每个元素表示测量计算基础状态 $_ket_n$的概率的振幅，其中 $ket\n} = \ket\n= [ket\b_{n]...b_1b_0_$为位\{$b_i\}$。 例如，在只分配两个量子位且处于量子状态的计算机上，$$_开始\对齐_ket_psi}{1}= _frac [sqrt]{2}\ket{00} - [frac]（1 ={2} i）]\ket，[end]###$${10}调用<xref:microsoft.quantum.diagnostics.dumpmachine>将生成此输出：

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一行按重要顺序提供具有相应量子位的的注释。
其余行描述以笛卡尔和极性格式测量基础状态向量 $_ket_n_$ 的概率振幅。 详细介绍第一行：

* **`∣0❭:`** 此行对应于`0`计算基础状态
* **`0.707107 +  0.000000 i`**：以笛卡尔格式表示的概率振幅。
* **` == `**：符号`equal`分离两个等效表示形式。
* **`**********  `**： 震级的图形表示，数量`*`与测量此状态矢量的概率成正比。
* **`[ 0.500000 ]`**：震级的数值
* **`    ---`**： 振幅相的图形表示（见下文）。
* **`[ 0.0000 rad ]`**：相位的数值（以弧度表示）。

大小和相位都显示图形表示。 幅度表示是直截了当的：它显示一个柱线`*`，柱值的概率越大。 对于相位，我们显示以下符号以表示基于范围的角度：

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

以下示例显示了`DumpMachine`某些常见状态：

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
  > qubit 的 ID 在运行时分配，它不一定与分配 qubit 的顺序或其在 qubit 寄存器中的位置保持一致。


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > 您可以通过在代码中放置断点并检查 qubit 变量的值来在 Visual Studio 中找出 qubit ID，例如：
  > 
  > ![在视觉工作室中显示 qubit ID](~/media/qubit_id.png)
  >
  > `0`索引上的`register2`qubit 具有 id=，`3`索引的 qubit`1`具有`2`id= 。

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 您可以通过使用<xref:microsoft.quantum.intrinsic.message>函数并传递消息中的 qubit 变量来找出 qubit ID，例如：
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 可以生成此输出：
  >```
  > 0=q:3; 1=q:2
  >```
  > 这意味着`0``register2`索引上的 qubit 具有 id_，`3`索引的 qubit`1`具有 id=`2`。


***

<xref:microsoft.quantum.diagnostics.dumpmachine>是命名空间的<xref:microsoft.quantum.diagnostics>一部分，因此为了使用它，您必须添加一个`open`语句：

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

<xref:microsoft.quantum.diagnostics.dumpregister>工作方式<xref:microsoft.quantum.diagnostics.dumpmachine>如下，只不过还需要一个量子位数组来将信息量限制为仅与相应量子位相关的信息量。

与<xref:microsoft.quantum.diagnostics.dumpmachine>，生成<xref:microsoft.quantum.diagnostics.dumpregister>的信息取决于目标计算机。 对于全态量子模拟器，它将波函数写入到量子子系统的全局阶段<xref:microsoft.quantum.diagnostics.dumpmachine>，该子系统由提供的量子位以与 的格式相同。  例如， 再次拍摄一台只分配两个量子位且处于量子状态的机器 $$开始 \ket_psi} = _frac{1}_sqrt{2}={00} ket - [frac[1 ={2} i]\ket{10} = - e_-i_pi/4{1}* （{2}[frac{0} ]sqrt = \ket -{2} [frac]（1 ={1} i）] \ket） \fc_-（1 = i）][sqrt]{2}\ket），[{0}结束]\align= $$$$$s 调用<xref:microsoft.quantum.diagnostics.dumpregister>生成`qubit[0]`此输出：

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

并调用<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[1]`生成此输出：

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

通常，与另一个寄存器纠缠的寄存器状态是混合状态，而不是纯状态。 在这种情况下，<xref:microsoft.quantum.diagnostics.dumpregister>输出以下消息：

```
Qubits provided (0;) are entangled with some other qubit.
```

下面的示例演示如何在 Q# 代码中使用<xref:microsoft.quantum.diagnostics.dumpregister>两<xref:microsoft.quantum.diagnostics.dumpmachine>者：

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

除了函数和`Assert``Dump`操作，Q# 还支持标准 Visual Studio 调试功能的子集：在模拟器上的代码执行期间，可以使用 F10[设置线断点](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[单步执行代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)以及[检查经典变量的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)。

在 Visual Studio 代码中的调试利用了由 OmniSharp 提供支持的 Visual Studio 代码扩展 C# 提供的调试功能，并且需要安装[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。 
