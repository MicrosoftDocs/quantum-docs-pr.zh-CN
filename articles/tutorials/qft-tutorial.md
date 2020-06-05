---
title: 在 Q 中编写和模拟 qubit 级程序#
description: 有关编写和模拟在单个 qubit 级别运行的量程程序的分步教程
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: 05d3292e1c6e3c8c1163c460f2aaa51c591aa1d5
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422234"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>教程：编写并模拟 qubit 中的程序\#

欢迎使用量程开发工具包教程，介绍如何编写和模拟在各个 qubits 上运行的基本量程计划。 

尽管 Q # 主要是作为大型的编程语言用于大规模的量程程序，但它也可以轻松地浏览更低级别的量程程序：直接解决特定的 qubits。
Q # 的灵活性允许用户从任何此类抽象级别中利用量程系统，在本教程中，我们将深入探讨 qubits 本身。
具体而言，我们将看一下[量程傅立叶转换](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)的组成部分，它是许多更大的量程算法的一个子例程。

请注意，通常以 "[量程线路](xref:microsoft.quantum.concepts.circuits)" 的形式描述这一低级别的量程信息处理方式，这种方式表示将入口的顺序应用到系统的特定 qubits。

因此，按顺序应用的单个和多个 qubit 操作可以在 "电路图" 中轻松表示。
在我们的示例中，我们将定义一个 Q # 操作来执行 qubit 的全部三次傅立叶傅立叶转换，并将以下表示形式作为线路：

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>先决条件

* 使用你首选的语言和开发环境[安装](xref:microsoft.quantum.install)量程开发工具包。
* 如果已安装 QDK，请确保将其[更新](xref:microsoft.quantum.update)至最新版本


## <a name="in-this-tutorial-youll-learn-how-to"></a>本教程介绍以下操作：

> [!div class="checklist"]
> * 在 Q 中定义量程运算#
> * 直接从命令行或使用传统主机程序调用 Q # 操作
> * 模拟从 qubit 分配到测量输出的量程操作
> * 观察量程系统的模拟 wavefunction 在整个操作过程中的演变方式

使用 Microsoft 的量程开发工具包运行量程程序通常包括两个部分：
1. 该程序本身是使用 Q # 量程编程语言实现的，然后调用以在量程计算机或量程模拟器上运行。 这些包括 
    - Q # 操作：作用于量程寄存器和 
    - Q # 函数：在量程算法内使用的传统子例程。
2. 用于调用量程程序并指定应在其上运行该程序的目标计算机的入口点。
    可以直接从命令行执行此操作，也可以通过使用一种传统编程语言（例如 Python 或 c #）编写的主机程序来完成此操作。
    本教程包括你喜欢的任何方法的说明。

## <a name="allocate-qubits-and-define-quantum-operations"></a>分配 qubits 并定义量程操作

本教程的第一部分包括定义 Q # 操作 `Perform3qubitQFT` ，该操作在三个 qubits 上执行量程傅立叶转换。 

此外，我们将使用 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 函数来观察三个 qubit 系统的模拟 wavefunction 在整个操作中的发展情况。

第一步是创建你的 Q # 项目和文件。
此操作的步骤取决于你将用于调用程序的环境，你可以在相应的[安装指南](xref:microsoft.quantum.install)中找到相关详细信息。

我们将逐步引导你完成文件的各个组件，但代码还可以作为完整的块提供。

### <a name="namespaces-to-access-other-q-operations"></a>用于访问其他 Q # 操作的命名空间
在该文件中，我们首先定义 `NamespaceQFT` 将由编译器访问的命名空间。
为了使我们的操作能够使用现有的 Q # 操作，我们打开了相关的 `Microsoft.Quantum.<>` 命名空间。

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>定义具有参数和返回的操作
接下来，我们定义 `Perform3qubitQFT` 操作：

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

现在，此操作不使用任何参数，并且不返回任何内容---在此示例中，我们编写了一个 `Unit` 对象，该对象在 Python 中类似于 `void` c # 或空元组 `Tuple[()]` 。
稍后，我们将对其进行修改以返回度量值的数组，此时 `Unit` 将替换该结果 `Result[]` 。 

### <a name="allocate-qubits-with-using"></a>将 qubits 分配给`using`
在我们的 Q # 操作中，我们首先使用以下语句分配三个 qubits 的寄存器 `using` ：

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

`using`在中，qubits 会自动分配到 $ \ket {0} $ 状态。 我们可以使用和来验证这一点 [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) ，后者将字符串和系统的当前状态打印到控制台。

> [!NOTE]
> `Message(<string>)`和 `DumpMachine()` 函数（ [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) 分别为和）直接打印到控制台。 就像实际的量程计算一样，Q # 不允许我们直接访问 qubit 状态。
> 但是， `DumpMachine` 当打印目标计算机的当前状态时，它可以在与完整状态模拟器结合使用时，为调试和学习提供有价值的见解。


### <a name="applying-single-qubit-and-controlled-gates"></a>应用单 qubit 和受控入口

接下来，应用组成操作本身的入口。
问 # 已在命名空间中包含许多基本的量程入口作为操作 [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ，并且这些都不是异常。 

在 Q # 操作中，调用 callables 的语句将按顺序执行。
因此，要应用的第一个入口是 [`H`](xref:microsoft.quantum.intrinsic.h) 第一个 qubit 的（Hadamard）：

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

若要将操作应用于寄存器中的特定 qubit （即 `Qubit` 从数组中的单个 `Qubit[]` ），我们使用标准索引表示法。
因此，将应用 [`H`](xref:microsoft.quantum.intrinsic.h) 到寄存器的第一个 qubit `qs` 将采用以下形式：

```qsharp
            H(qs[0]);
```

除了将 `H` （Hadamard）入口应用于单个 qubits 外，QFT 线路主要包括受控 [`R1`](xref:microsoft.quantum.intrinsic.r1) 旋转。
`R1(θ, <qubit>)`通常，操作会保持 qubit 的 $ \ket {0} $ 组件不变，同时应用 $e ^ {i\theta} $ 的旋转到 $ \ket {1} $ 组件。

#### <a name="controlled-operations"></a>受控操作

Q # 使在一个或多个控件 qubits 上执行操作的条件非常简单。
通常，我们只是将调用置于 `Controlled` ，并将操作参数更改为：

 `Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` 。

请注意，控件 qubits 必须作为数组提供，即使它是单个 qubit。

`H`接下来，我们发现，下一步是在 `R1` 第一个 qubit 上操作（并由第二个/第三个控制）：

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

我们称之为

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

请注意，我们使用 [`PI()`](xref:microsoft.quantum.math.pi) [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) 命名空间中的函数来定义 pi 弧度的旋转。
此外，我们将除以 `Double` （例如）， `2.0` 因为除以整数 `2` 将引发类型错误。 

> [!TIP]
> `R1(π/2)`和 `R1(π/4)` 等效于 `S` 和 `T` 操作（也在中 `Microsoft.Quantum.Intrinsic` ）。


`H`对第二个和第三个 qubits 应用相关操作和受控旋转后：

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

我们只需要应用 [`SWAP`](xref:microsoft.quantum.intrinsic.swap) 入口来完成线路：

```qsharp
            SWAP(qs[2], qs[0]);
```

这是必需的，因为量程傅立叶转换的性质会按相反的顺序输出 qubits，因此交换允许将子例程无缝集成到更大的算法。

因此，我们已将量程傅立叶转换的 qubit 级操作写入到 Q # 操作中：

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

但是，我们现在不能调用它。
我们分配的 qubits 是 $ \ket {0} $，在我们分配它们时，在 "问题解答" 中，我们应该按照与我们相同的方式（或更好的方式）来保留。

### <a name="deallocate-qubits"></a>解除分配 qubits

我们 [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) 再次调用来查看操作后状态，最后应用 [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) 于 qubit 注册，以便在完成操作之前将 qubits 重置为 $ \ket {0} $：

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

要求将所有释放的 qubits 显式设置为 $ \ket {0} $ 是 Q # 的基本功能，因为当它们开始使用相同的 qubits （一种稀有资源）时，它允许其他操作准确地了解其状态。
此外，这可确保它们不会与系统中的任何其他 qubits 放大。
如果在分配块结束时未执行重置 `using` ，则将引发运行时错误。

完整的 Q # 文件现在应如下所示：

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


完成 Q # 文件和操作后，我们的量程计划就可以被调用并进行模拟。

## <a name="execute-the-program"></a>执行程序

在文件中定义了 Q # 操作后 `.qs` ，我们现在需要调用该操作并观察返回的任何传统数据。
目前，没有返回任何内容（回想一下，上面定义的操作返回了 `Unit` ），但当我们稍后修改 Q # 操作来返回测量结果（）的数组时 `Result[]` ，我们将解决此问题。

尽管 Q # 计划在用于调用它的环境中无处不在，但这样做的方式当然会有所不同。 因此，只需按照与设置相对应的选项卡中的说明进行操作：使用 Q # 命令行应用程序，或使用 Python 或 c # 中的主机程序。

#### <a name="command-line"></a>[命令行](#tab/tabid-cmdline)

若要从命令行运行 Q # 程序，只需对 Q # 文件进行少量更改。

只需在 `@EntryPoint()` 操作定义之前添加一行：

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

若要运行程序，请打开项目的文件夹中的终端并输入

```dotnetcli
dotnet run
```

执行时，应会 `Message` `DumpMachine` 在控制台中看到以下输出和输出。


#### <a name="python"></a>[Python](#tab/tabid-python)

创建 Python 主机文件： `host.py` 。

主机文件的构造如下所示： 
1. 首先，导入 `qsharp` 模块，该模块将注册 Q # 互操作性的模块加载程序。 
    这允许问 # 命名空间（例如 `NamespaceQFT` 我们在 Q # 文件中定义的命名空间）显示为 Python 模块，可以从该模块中导入 q # 操作。
2. 然后，导入在此示例中将直接调用---的 Q # 操作 `Perform3qubitQFT` 。
    我们只需要将入口点导入到 Q # 程序（即，_不_是像和这样的操作 `H` `R1` ，而是由其他 Q # 操作调用，而不是由传统主机使用）。
3. 在模拟 Q # 操作或函数中，使用窗体 `<Q#callable>.simulate(<args>)` 在目标计算机上运行这些操作 `QuantumSimulator()` 。 

> [!NOTE]
> 如果我们要在另一台计算机上调用该操作，例如 `ResourceEstimator()` ，只需使用即可 `<Q#callable>.estimate_resources(<args>)` 。
> 通常，Q # 操作对于运行它们的计算机是不可知的，但某些功能（例如）的 `DumpMachine` 行为可能有所不同。

4. 执行模拟时，操作调用将返回 Q # 文件中定义的值。
    目前没有返回任何内容，但稍后我们将显示分配和处理这些值的示例。
    通过我们的数据和完全传统的结果数据，我们可以执行所需的任何操作。

你的完整 `host.py` 文件应如下所示：

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

运行 Python 文件，并在控制台中打印，应会看到 `Message` `DumpMachine` 以下输出。 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

按照[安装指南](xref:microsoft.quantum.install.cs)中的说明进行操作，创建一个 c # 主机文件，然后将其重命名为 `host.cs` 。

C # 宿主有四部分：
1. 构造量子模拟器。
    在下面的代码中，这是一个变量 `qsim` 。
2. 计算量子算法所需的任何参数。
    在此示例中，没有任何内容。
3. 运行量子算法。 
    每个 Q# 运算都会生成名称相同的 C# 类。 
    此类具有“异步”执行运算的 `Run` 方法。
    执行是异步的，因为实际硬件上的执行将是异步的。 
    由于 `Run` 方法是异步的，因此我们调用 `Wait()` 方法; 这会阻止执行，直到任务完成并同步返回结果。 
4. 处理返回的操作结果。
    现在，操作不返回任何内容。


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
运行应用程序，输出应与下面的匹配。
按下键后，程序将退出。
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

在全状态模拟器上调用时， `DumpMachine()` 提供量程状态的 wavefunction 的这些多种表示形式。 $N $-qubit 系统可能的状态可由 $ 2 ^ n $ 计算基础状态表示，每个状态都具有相应的复杂系数（只是一种振幅和一个阶段）。
计算基础状态对应于 $n $---长度的所有可能的二进制字符串，即 qubit 状态 $ \ket {0} $ 和 $ \ket $ 的所有可能组合 {1} ，其中每个二进制数字对应于单个 qubit。

第一行提供了一个注释，其中包含相应 qubits 的 Id。
`2`最重要的是，Qubit 是指在基本状态向量 $ \ket{i} $ 的二进制表示形式中，Qubit 的状态对应于 `2` 最左侧的数字。 例如，$ \ket {6} = \ket {110} $ 包含 qubits `2` ，以及 $ \ket $ `1` {1} 和 qubit in `0` $ \ket {0} $。


其余行说明了度量基准状态向量 $ \ket{i} $ 在笛卡尔和极坐标中的概率幅度。
详细了解输入状态 $ \ket $ 的第一行 {000} ：
* **`|0>:`** 此行对应于 `0` 计算基础状态（假设我们的初始状态为 {000} "\ket $"，我们预计这是在此时具有概率幅度的唯一状态）。
* **`1.000000 +  0.000000 i`**：以笛卡尔格式的概率幅度。
* **` == `**： `equal` 符号分隔等效表示形式。
* **`********************`**：大小的图形表示形式，的数量与 `*` 度量此状态向量的概率成正比。 
* **`[ 1.000000 ]`**：量值的数值
* **`    ---`**：振幅阶段的图形化表示形式。
* **`[ 0.0000 rad ]`**：阶段的数值（以弧度为单位）。

大小和阶段都以图形表示形式显示。 大小表示形式非常简单：显示一个的条形 `*` ，并显示更大的概率。 对于阶段，请参阅[测试和调试：](xref:microsoft.quantum.guide.testingdebugging#dump-functions)基于角度范围的可能符号表示形式的转储函数。


因此，打印输出说明了我们的程控入口从

$ $ \ket{\psi} \_ {初始} = \ket {000} $ $

to 

$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left （\ket {000} + \ket + {001} \ket {010} + \ket + \ket + {011} {100} \ket {101} + \ket {110} + \ket {111} \right） \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}，\end{align} $ $

这是 qubit 傅立叶转换的确切行为。 

如果你对其他输入状态的影响有了影响，我们建议你在转换前通过应用 qubit 操作来解决。

## <a name="adding-measurements"></a>添加度量值

遗憾的是，量程机制的基石告诉我们，真正的量程系统不能有这样的 `DumpMachine` 功能。 相反，我们会被迫通过量化指标提取信息，通常情况下，这种情况不仅能提供完整的量程状态，而且还可以显著改变系统本身。
有很多种类的量程度量，但我们将重点介绍单个 qubits 上的最基本的： projective 度量值。
根据给定的度量值（例如，计算基础 $ \{ \ket {0} ，\ket {1} \} $），将 qubit 状态投影到衡量的任何基准状态---因此会破坏两者之间的任何 superposition。

若要在 Q # 计划内实现度量，我们使用的是的 `M` 操作 `Microsoft.Quantum.Intrinsic` ，该操作返回一个 `Result` 类型。

首先，我们修改 `Perform3QubitQFT` 操作以返回度量结果的数组， `Result[]` 而不是 `Unit` 。

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>定义和初始化 `Result[]` 数组

在分配 qubits （即在 `using` 语句之前）之前，我们声明并绑定此数组（ `Result` 每个 qubit 一个）： 

```qsharp
        mutable resultArray = new Result[3];
```

关键字 "靠上" `mutable` `resultArray` 允许稍后在代码中重新绑定变量---例如，添加度量结果时。

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>在循环中执行度量 `for` ，并向数组中添加结果

在块内的 "傅立叶转换" 操作之后 `using` ，插入以下代码：

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)在数组上调用的函数（例如，qubits 的数组）将 `qs` 返回数组的索引范围。 在这里，我们将在循环中使用它， `for` 以按顺序使用语句度量每个 qubit `M(qs[i])` 。
然后，将每个测量的 `Result` 类型（ `Zero` 或 `One` ）添加到中的相应索引位置， `resultArray` 并使用更新和重新分配语句。

> [!NOTE]
> 此语句的语法对 Q # 是唯一的，但与 `resultArray[i] <- M(qs[i])` 其他语言（如 F # 和 R）中所示的类似变量重新分配相对应。

关键字 `set` 始终用于重新分配使用绑定 `mutable` 的变量。

#### <a name="return-resultarray"></a>返回`resultArray`

所有三个 qubits 都得到了度量，并将结果添加到了 `resultArray` 中，我们就可以像以往一样重置和解除分配 qubits。
`using`块关闭后，插入

```qsharp
        return resultArray;
```
最终返回操作的输出。 

### <a name="understanding-the-effects-of-measurement"></a>了解度量值的效果

让我们将函数的位置更改 `DumpMachine` 为在测量前后输出状态。
最终的操作代码应如下所示： 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

如果是从命令行运行，则在执行结束时，只会将返回的数组直接打印到控制台。
否则，请更新主机程序来处理返回的数组。

#### <a name="command-line"></a>[命令行](#tab/tabid-cmdline)

为了更好地理解将在控制台中打印的返回数组，我们可以 `Message` 在该语句前面的 Q # 文件中添加另一个 `return` 。

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

运行该项目，输出应如下所示：

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

将 Python 计划更新为以下内容：

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

运行该文件，输出应如下所示：

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

现在，我们的操作返回了结果，请将方法调用替换 `Wait()` 为获取 `Result` 属性。 这仍可实现前面讨论的相同 synchronicity，可以直接将此值绑定到变量 `measurementResult` 。

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

运行该项目，输出应如下所示：

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

此输出显示了几个不同的内容：
1. 将返回的结果与预度量值进行比较 `DumpMachine` 时，它_not_清楚地说明了 QFT superposition over 基础状态。
    度量仅返回单基准状态，其概率由系统的 wavefunction 中该状态的幅度决定。
2. 从下度量值开始 `DumpMachine` ，我们会看到，量化指标_更改_了状态本身，并将其从初始 superposition over 基数状态投影到对应于度量值的单一基准状态。

如果要重复执行此操作多次，就会看到结果统计信息开始，说明 QFT 状态的 superposition，这会给每个拍摄产生随机结果。
_不过_，除了效率低下且仍完善，这只会重现基础状态的相对 amplitudes，而不是它们之间的相对阶段。
在此示例中，后者不是问题，但如果给 QFT 的输入更为复杂，则会看到相对阶段 {000} 。

#### <a name="partial-measurements"></a>部分度量 
若要浏览仅测量寄存器的某些 qubits 可能会影响系统状态的方式，请尝试将以下内容添加到循环中的 `for` 测量行之后：
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

请注意，若要访问函数，则 `IntAsString` 必须添加 
```qsharp
    open Microsoft.Quantum.Convert;
```
命名空间语句的其余部分 `open` 。

在生成的输出中，你将看到逐步投影到 subspaces，因为每个 qubit 都进行了度量。


## <a name="use-the-q-libraries"></a>使用 Q # 库
正如我们在简介中所提到的，很多 Q # 的强大功能都是因为它使您能够抽象掉处理个别 qubits 的问题。
当然，如果您想要开发完全规模的适用量程程序，请考虑某个操作是 `H` 在特定旋转之前还是之后才会减慢您的速度。 

Q # 库包含[QFT](xref:microsoft.quantum.canon.qft)操作，你可以简单地执行此操作，并将其应用于任意数量的 qubits。
为此，请在 Q # 文件中定义一个新操作，该操作具有相同的内容 `Perform3QubitQFT` ，但从第一个 `H` 到的内容替换为 `SWAP` 两个简单的行：
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
第一行只是创建 [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) qubits 的已分配数组的表达式，即 `qs` [QFT](xref:microsoft.quantum.canon.qft)操作将其作为参数。
这对应于寄存器中 qubits 的索引排序。

若要访问这些操作，请 `open` 在 Q # 文件的开头为其各自的命名空间添加语句：
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

现在，调整主机程序以调用新操作的名称（例如 `PerformIntrinsicQFT` ），并为其试。

若要查看使用 Q # 库操作的实际优点，请将 qubits 数改为 `3` 以下值：
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
因此，你可以为任何给定数量的 qubits 应用适当的 QFT，而不必担心 `H` 每个 qubit 上的新操作和循环的混乱。

请注意，在你增加---qubits 的数量时，量程模拟器会以指数方式更长的时间来运行，因为这会使我们期待真实的量程硬件！













