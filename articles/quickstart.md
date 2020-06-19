---
title: 通过 Q# 探索纠缠
description: 了解如何在 Q# 中编写量子程序。 使用 Quantum 开发工具包 (QDK) 开发 Bell 态应用程序
author: natke
ms.author: nakersha
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 271eb7f496835f152573be930d0fe24e59f2d15d
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630076"
---
# <a name="tutorial-explore-entanglement-with-q"></a>教程：通过 Q\# 探索纠缠

在本教程中，我们演示如何编写一个 Q# 程序，用于操作和测量量子比特并演示叠加和纠缠效果。
我们可以据此安装 QDK、生成程序并在量子模拟器上执行该程序。  

我们将编写一个用于演示量子纠缠的名为 Bell 的应用程序。
Bell 这一名称是指 Bell 状态，即两个量子位的特定量子状态，用于表示叠加和量子纠缠的最简单示例。

## <a name="prerequisites"></a>先决条件

如果准备开始编码，请在继续之前按照以下步骤操作： 

* 安装适用于 [Python](xref:microsoft.quantum.install.python) 或 [.NET](xref:microsoft.quantum.install.cs) 的量子开发工具包。
* 如果已安装 QDK，请确保将其[更新](xref:microsoft.quantum.update)至最新版本

也可以阅读说明而不安装 QDK，查看 Q# 编程语言的概述和基本的量子计算概念。

## <a name="demonstrating-qubit-behavior-with-q"></a>使用 Q# 演示量子位行为

回想一下简单的[量子位定义](xref:microsoft.quantum.overview.understanding)。  经典位保存单个二进制值（如 0 或 1），而[量子位](xref:microsoft.quantum.glossary#qubit)的状态则可以是 0 和 1 的**叠加**。  从概念上讲，可以将量子位视为空间中的方向（也称为矢量）。  量子位可以是任何可能的方向。 两个**经典状态**是两个方向，一个方向表示度量结果为 0 的可能性为 100%，另一个方向表示度量结果为 1 的可能性为 100%。  这种表示方式也可通过 [Bloch 球](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)更正式地可视化。

度量行为会生成二进制结果并改变量子位状态。 度量会生成一个二进制值（0 或 1）。  量子位从叠加态（任何方向）变为经典状态之一。  随后，在没有任何干预操作的情况下重复进行相同的度量会生成相同的二进制结果。  

多个量子位可以[**纠缠**](xref:microsoft.quantum.glossary#entanglement)在一起。 度量一个纠缠的量子位时，就会知道另一个量子位的状态。

现在，我们可以演示如何通过 Q# 来表达这种行为了。  一开始可以编写并生成一个最简单的程序，用于演示量子叠加和量子纠缠。

## <a name="setup"></a>设置

本教程使用一个主机程序，并且由两部分组成：

1. 使用 Q# 量子编程语言实现的一系列量子算法。
1. 使用 Python 或 C# 实现且充当主入口点并调用 Q# 运算来执行量子算法的主机程序。

#### <a name="python"></a>[Python](#tab/tabid-python)

1. 为应用程序选择一个位置

1. 创建名为 `Bell.qs` 的文件。 此文件将包含你的 Q# 代码。

1. 创建名为 `host.py` 的文件。 此文件将包含你的 Python 主机代码。

#### <a name="c-command-line"></a>[C# 命令行](#tab/tabid-csharp)

1. 创建新的 Q# 项目：

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    你将看到一个 `.csproj` 文件、一个名为 `Operations.qs` 的 Q# 文件，以及一个名为 `Driver.cs` 的主机程序文件

1. 对 Q# 文件重命名

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. 创建新项目

   * 打开 Visual Studio
   * 转到“文件”菜单并选择“新建” -> “项目...”  
   * 在项目模板资源管理器的搜索字段中键入 `Q#`，然后选择 `Q# Application` 模板
   * 将项目命名为 `Bell`

1. 对 Q# 文件重命名

   * 导航到“解决方案资源管理器”
   * 右键单击 `Operations.qs` 文件
   * 将其重命名为 `Bell.qs`

* * *

## <a name="write-a-q-operation"></a>编写 Q# 运算

我们的目标是准备两个处于特定量子状态的量子位，演示如何通过 Q# 操作量子位，以便更改其状态并演示叠加和纠缠效果。 我们将逐步完成这一切，以演示量子位状态、操作和度量。

**概述：** 在下面的第一个代码中，我们演示如何在 Q# 中操作量子位。  我们将引入两个操作（`M` 和 `X`）来转换量子位的状态。 

在此代码片段中，我们定义了操作 `Set`。该操作使用一个量子位作为参数，使用另一个参数 (`desired`) 来表示我们希望该量子位呈现的状态。  操作 `Set` 使用操作 `M` 对量子位进行度量。  在 Q# 中，量子位的度量始终返回 `Zero` 或 `One`。  如果度量返回的值不等于所需的值，Set 会“翻转”该量子位；也就是说，它会执行 `X` 操作，将量子位状态变为新状态，使度量时返回 `Zero` 和 `One` 的概率反转。  为了演示 `Set` 操作的效果，我们接着添加了 `TestBellState` 操作。  此操作以 `Zero` 或 `One` 作为输入，使用该输入调用 `Set` 操作特定的次数，然后计算对量子位进行度量时返回 `Zero` 的次数和返回 `One` 的次数。 当然，在第一次对 `TestBellState` 操作进行这样的模拟时，我们预期输出会表明：在将 `Zero` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `Zero`；在将 `One` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `One`。  接下来，我们会向 `TestBellState` 添加代码，演示叠加和纠缠。


### <a name="q-operation-code"></a>Q# 运算代码

1. 将 Bell.qs 文件的内容替换为以下代码：

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    现在可以调用此操作，将量子位设置为经典状态：100% 的情况下返回 `Zero`，或者 100% 的情况下返回 `One`。  `Zero` 和 `One` 为常量，表示对量子位进行度量时仅有的两个可能结果。

    操作 `Set` 用于度量量子位。
    如果量子位处于所需状态，`Set` 会将其保留，否则会执行 `X` 操作，将量子位状态更改为所需状态。

### <a name="about-q-operations"></a>关于 Q# 运算

Q# 操作是量子子例程。 也就是说，它是一个包含量子操作的可调用例程。

运算的参数在括号内指定为元组。

运算的返回类型在冒号之后指定。 根据这个规则，`Set` 运算表示没有返回类型，因此将标记为返回 `Unit`。 此 Q# 运算等效于 F# 中的 `unit`，大致类似于 C# 中的 `void` 和 Python 中的空元组 (`Tuple[()]`)。

在第一个 Q# 操作中，我们已经使用了两个量子操作：

* [M](xref:microsoft.quantum.intrinsic.m) 操作，用于度量量子位的状态
* [X](xref:microsoft.quantum.intrinsic.x) 操作，用于翻转量子位的状态

量子操作可转换量子位的状态。 有时候，人们在讨论时会使用与经典“逻辑门”类似的“量子门”（而不是“量子操作”）这一术语。 这种习惯根源于早期的量子计算时代。那时候，算法只是一种理论构造，以图形（类似于经典计算中的线路图）方式表示。

### <a name="add-q-test-code"></a>添加 Q# 测试代码

1. `Set` 运算结束后，在命名空间内将以下运算添加到 `Bell.qs` 文件：

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    此运算 (`TestBellState`) 将循环执行 `count` 迭代，在量子位上设置指定的 `initial` 值，然后对结果进行度量 (`M`)。 它将收集我们所度量的 0 和 1 的个数统计信息，并将其返回给调用方。 它执行另一个必需的运算。 它将量子位重置为已知状态 (`Zero`)，然后将其返回，使其他人可以在已知状态下分配此量子位。 这是 `using` 语句所必需的。

### <a name="about-variables-in-q"></a>关于 Q# 中的变量

默认情况下，Q# 中的变量是不可变的；它们的值在绑定后将不能更改。 `let` 关键字用于指示不可变变量的绑定。 运算参数始终是不可变的。

如果需要可以更改值的变量（如示例中的 `numOnes`），可以使用 `mutable` 关键字声明该变量。 使用 `set` 语句可以更改可变变量的值。

在这两种情况下，编译器都会推断变量的类型。 Q# 不需要为变量提供任何类型批注。

### <a name="about-using-statements-in-q"></a>关于 Q# 中的 `using` 语句

Q# 中的 `using` 语句也很特殊。 它用于分配要在代码块中使用的量子位。 在 Q# 中，所有量子位都是动态分配和释放的，而不是在复杂算法的整个生命周期内都存在的固定资源。 `using` 语句在代码块的开头分配一组量子位，并在代码块的末尾释放这些量子位。

## <a name="create-the-host-application-code"></a>创建主机应用程序代码

#### <a name="python"></a>[Python](#tab/tabid-python)

1. 打开 `host.py` 文件，并添加以下代码：

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. 将 `Driver.cs` 文件的内容替换为以下代码：

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>关于主机应用程序代码

#### <a name="python"></a>[Python](#tab/tabid-python)

Python 主机应用程序包含三个部分：

* 计算量子算法所需的任何参数。 在示例中，`count` 固定为 1000，`initial` 是量子位的初始值。
* 通过调用所导入 Q# 运算的 `simulate()` 方法来运行量子算法。
* 处理运算结果。 在示例中，`res` 接收运算的结果。 此结果是模拟器所度量 0 的个数 (`num_zeros`) 和 1 的个数 (`num_ones`) 的元组。 我们通过析构元组来获取两个字段，然后打印结果。

#### <a name="c"></a>[C#](#tab/tabid-csharp)

C# 主机应用程序包含四个部分：

* 构造量子模拟器。 在示例中，`qsim` 是模拟器。
* 计算量子算法所需的任何参数。 在示例中，`count` 固定为 1000，`initial` 是量子位的初始值。
* 运行量子算法。 每个 Q# 运算都会生成名称相同的 C# 类。 此类具有“异步”执行运算的 `Run` 方法。 执行是异步的，因为实际硬件上的执行将是异步的。 由于 `Run` 方法是异步的，因此我们提取 `Result` 属性；这会阻止执行，直到任务完成并以同步方式返回结果。
* 处理运算结果。 在示例中，`res` 接收运算的结果。 此结果是模拟器所度量 0 的个数 (`numZeros`) 和 1 的个数 (`numOnes`) 的元组。 在 C# 中这会以 ValueTuple 的形式返回。 我们通过析构元组来获取两个字段，打印结果并等待按键。

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>生成并运行

#### <a name="python"></a>[Python](#tab/tabid-python)

1. 在终端运行以下命令：

    ```
    python host.py
    ```

    此命令将运行模拟 Q# 运算的主机应用程序。

结果应为：

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[命令行/Visual Studio Code](#tab/tabid-csharp)

1. 在终端运行以下命令：

    ```dotnetcli
    dotnet run
    ```

    此命令将自动下载所需的全部包，生成应用程序，然后在命令行中运行该应用程序。

1. 或者，按下 F1 打开命令面板，并选择“调试: 在不调试的情况下启动” 。
系统可能会提示你创建新的 ``launch.json`` 文件，以描述如何启动程序。
默认 ``launch.json`` 适用于大多数应用程序。

结果应为：

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. 只需点击 `F5`，便可生成并运行程序！

结果应为：

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

按下键后，程序将退出。

* * *

## <a name="prepare-superposition"></a>准备叠加

**概述** 现在，让我们看看 Q# 如何表达将量子位置于叠加态的方式。  回想一下，量子位的状态可以是 0 和 1 的叠加。  为了实现这种叠加，我们将使用 `Hadamard` 操作。 如果量子位处于任一经典状态（度量始终返回 `Zero` 或始终返回 `One`），则 `Hadamard`（简称 `H`）操作会将量子位置于这样一种状态：对量子位进行度量时，50% 的情况下会返回 `Zero`，50% 的情况下会返回 `One`。  从概念上讲，可以将此量子位视为介于 `Zero` 和 `One` 之间的一种中间状态。  现在，我们在模拟 `TestBellState` 操作时会看到度量后的结果会大致返回相等数量的 `Zero` 和 `One`。  

首先，我们来尝试翻转量子位（如果量子位为 `Zero` 状态，则会翻转为 `One`，反之亦然）。 操作步骤：先执行 `X` 操作，然后在 `TestBellState` 操作中度量它：

```qsharp
X(qubit);
let res = M(qubit);
```

现在结果将翻转（按下 `F5` 后）：

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

但到目前为止，我们所看到的都是经典运算。 接下来，我们来获取量子结果。 我们需要做的就是将上一个运行中的 `X` 操作替换为 `H`（全称为 Hadamard）操作。 我们不会将所有量子位都从 0 翻转到 1，而是只翻转一半。 `TestBellState` 中的替换行现在如下所示：

```qsharp
H(qubit);
let res = M(qubit);
```

现在，结果变得更加有趣：

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

每次度量状态时，我们都会请求一个经典值，但量子位的 0 和 1 值各占一半，因此从统计学角度而言，我们得到的 0 和 1 各占一半。 这称为“叠加”，它让我们对量子状态有了一个初步的认识。

## <a name="prepare-entanglement"></a>准备展示纠缠

**概述：** 现在，让我们看看 Q# 如何表达纠缠量子位的方式。  首先，我们将第一个量子位设置为初始状态，然后使用 `H` 操作将其置于叠加状态。  接着，在度量第一个量子位之前，我们使用一个新的操作（`CNOT`，代表“可控非”）。  对两个量子位执行此操作的结果是，在第一个量子位是 `One` 的情况下翻转第二个量子位。  现在，这两个量子位纠缠在一起。  第一个量子位的统计信息没有变化（在度量后，`Zero` 和 `One` 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同。 `CNOT` 把这两个量子位纠缠在了一起，因此，不论其中一个发生什么，另一个也会同样发生。 如果翻转度量值（先翻转第二个量子位，再翻转第一个），会发生相同的情况。 第一个度量值是随机的，第二个将与第一个同步。

我们需要做的第一件事是分配 2 个量子位，而不是在 `TestBellState` 中分配 1 个量子位：

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

在这种情况下，我们可以先添加一个新操作 (`CNOT`)，再在 `TestBellState` 中度量 (`M`)：

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

我们还添加了另一个 `Set` 运算，用于初始化第一个量子位，以确保启动时它始终处于 `Zero` 状态。

我们还需要重置第二个量子位，然后再将其释放。

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

完整的例程现在如下所示：

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

如果我们运行这段代码，我们将获得与之前相同的 0 和 1 各占一半的结果。 但是，我们想要知道第二个量子位如何响应所度量的第一个量子位。 我们将使用 `TestBellState` 运算的新版本来添加此统计信息：

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

新的返回值 (`agree`) 会跟踪第一个量子位的度量值与第二个量子位的度量值相同的次数。 我们还需要相应地更新主机应用程序：

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

现在，运行代码，我们将会得到非常惊人的结果：

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

如概述中所述，第一个量子位的统计信息没有变化（0 和 1 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同，因为这两个量子位已纠缠在一起！

恭喜，你已经编写了第一个量子程序！

## <a name="next-steps"></a>后续步骤

[Grover 搜索](xref:microsoft.quantum.quickstarts.search)教程介绍了如何生成并运行 Grover 搜索（最常用的量子计算算法之一），并通过一个很好的 Q# 程序示例演示了如何使用量子计算来解决实际问题。  

[量子开发工具包入门](xref:microsoft.quantum.welcome)建议了更多的学习 Q# 和量子编程的方法。
