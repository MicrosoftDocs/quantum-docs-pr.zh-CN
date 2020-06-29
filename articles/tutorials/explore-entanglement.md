---
title: 通过 Q# 探索纠缠
description: 了解如何在 Q# 中编写量子程序。 使用 Quantum 开发工具包 (QDK) 开发 Bell 态应用程序
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 16c93b3dd17363c06602529cb34e8fc84aadc7a8
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415416"
---
# <a name="tutorial-explore-entanglement-with-q"></a>教程：通过 Q\# 探索纠缠

在本教程中，我们演示如何编写一个 Q# 程序，用于操作和测量量子比特并演示叠加和纠缠效果。

我们将编写一个用于演示量子纠缠的名为 Bell 的应用程序。
Bell 这一名称是指 Bell 状态，即两个量子位的特定量子状态，用于表示叠加和量子纠缠的最简单示例。

## <a name="pre-requisites"></a>先决条件

如果准备开始编码，请在继续之前按照以下步骤操作： 

* 使用你首选的语言和开发环境[安装](xref:microsoft.quantum.install)量程开发工具包。
* 如果已安装 QDK，请确保将其[更新](xref:microsoft.quantum.update)至最新版本

你还可以在不安装 QDK 的情况下遵循这些叙述，并查看 Q # 编程语言的概述以及量程计算的第一概念。

## <a name="in-this-tutorial-youll-learn-how-to"></a>在本教程中，你将了解：

> [!div class="checklist"]
> * 在 Q 中创建和合并操作\#
> * 创建操作，将 qubits 置于 superposition、entangle 中并度量它们。
> * 演示在模拟器中运行 Q # 程序的量程牵连。 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>通过 QDK 演示 qubit 行为

经典位保存单个二进制值（如 0 或 1），而[量子位](xref:microsoft.quantum.glossary#qubit)的状态则可以是 0 和 1 的**叠加**。  从概念上讲，qubit 的状态可以看作是抽象空间（也称为矢量）中的方向。  Qubit 状态可以为任何可能的方向。 两个**经典状态**是两个方向，一个方向表示度量结果为 0 的可能性为 100%，另一个方向表示度量结果为 1 的可能性为 100%。

度量行为会生成二进制结果并改变量子位状态。
度量值生成一个二进制值，0或1。  量子位从叠加态（任何方向）变为经典状态之一。  随后，在没有任何干预操作的情况下重复进行相同的度量会生成相同的二进制结果。  

多个量子位可以[**纠缠**](xref:microsoft.quantum.glossary#entanglement)在一起。  度量一个纠缠的量子位时，就会知道另一个量子位的状态。

现在，我们可以演示如何通过 Q# 来表达这种行为了。  一开始可以编写并生成一个最简单的程序，用于演示量子叠加和量子纠缠。

## <a name="creating-a-q-project"></a>创建 Q # 项目

首先，我们要做的就是创建一个新的 Q # 项目。 在本教程中，我们将使用基于[命令行应用程序 VS Code](xref:microsoft.quantum.install.standalone)的环境。

若要创建新项目，请在 VS Code 中： 

1. 单击 "**查看**" "  ->  **命令面板**"，然后选择 " **Q #：创建新项目**"。
2. 单击 "**独立控制台应用程序**"。
3. 导航到要保存项目的位置，然后单击 "**创建项目**"。
4. 成功创建项目后，单击右下方的 "**打开新项目 ...** "。

在此示例中，我们调用了项目 `Bell` 。 这会生成两个文件： `Bell.csproj` 、项目文件和 `Program.qs` ，我们将使用该模板来编写应用程序的 Q # 应用程序模板。 的内容 `Program.qs` 应为：

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>编写 Q \# 应用程序
 
我们的目标是准备两个处于特定量子状态的量子位，演示如何通过 Q# 操作量子位，以便更改其状态并演示叠加和纠缠效果。 我们将构建这一段内容，以引入 qubit 状态、操作和度量。

### <a name="initialize-qubit-using-measurement"></a>使用度量值初始化 qubit

在下面的第一个代码中，我们演示如何在 Q# 中操作量子位。  我们将介绍两个操作，这些操作将 [`M`](xref:microsoft.quantum.intrinsic.m) [`X`](xref:microsoft.quantum.intrinsic.x) 转换 qubit 的状态。 在此代码片段中，我们定义了操作 `SetQubitState`。该操作使用一个量子位作为参数，使用另一个参数 (`desired`) 来表示我们希望该量子位呈现的状态。  操作 `SetQubitState` 使用操作 `M` 对量子位进行度量。  在 Q # 中，qubit 度量值始终返回 `Zero` 或 `One` 。  如果度量值返回一个不等于所需值的值，则 `SetQubitState` "翻转" qubit; 也就是说，它将执行一个 `X` 操作，该操作会将 qubit 状态更改为一种新状态，在该状态下，测量的概率返回 `Zero` 并 `One` 反转。 这样，就 `SetQubitState` 始终将目标 qubit 置于所需状态。

将的内容替换为 `Program.qs` 以下代码：


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

现在可以调用此操作，将量子位设置为经典状态：100% 的情况下返回 `Zero`，或者 100% 的情况下返回 `One`。
`Zero` 和 `One` 为常量，表示对量子位进行度量时仅有的两个可能结果。

操作 `SetQubitState` 用于度量量子位。 如果量子位处于所需状态，`SetQubitState` 会将其保留，否则会执行 `X` 操作，将量子位状态更改为所需状态。

#### <a name="about-q-operations"></a>关于 Q# 运算

Q# 操作是量子子例程。 也就是说，它是包含对其他量程操作的调用的可调用例程。

运算的参数在括号内指定为元组。

运算的返回类型在冒号之后指定。 根据这个规则，`SetQubitState` 运算表示没有返回类型，因此将标记为返回 `Unit`。 此 Q# 运算等效于 F# 中的 `unit`，大致类似于 C# 中的 `void` 和 Python 中的空元组 (`Tuple[()]`)。

在第一个 Q# 操作中，我们已经使用了两个量子操作：

* [`M`](xref:microsoft.quantum.intrinsic.m)操作，它测量 qubit 的状态
* [`X`](xref:microsoft.quantum.intrinsic.x)操作，该操作将反转 qubit 的状态

量子操作可转换量子位的状态。 有时候，人们在讨论时会使用与经典“逻辑门”类似的“量子门”（而不是“量子操作”）这一术语。 这种习惯根源于早期的量子计算时代。那时候，算法只是一种理论构造，以图形（类似于经典计算中的线路图）方式表示。

### <a name="counting-measurement-outcomes"></a>统计度量结果

为了演示 `SetQubitState` 操作的效果，我们接着添加了 `TestBellState` 操作。 此操作以 `Zero` 或 `One` 作为输入，使用该输入调用 `SetQubitState` 操作特定的次数，然后计算对量子位进行度量时返回 `Zero` 的次数和返回 `One` 的次数。 当然，在第一次对 `TestBellState` 操作进行这样的模拟时，我们预期输出会表明：在将 `Zero` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `Zero`；在将 `One` 作为参数输入的情况下，对量子位集进行的所有度量都会返回 `One`。 接下来，我们将向 `TestBellState` 演示 superposition 和牵连添加代码。

`SetQubitState` 运算结束后，在命名空间内将以下运算添加到 `Bell.qs` 文件：

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
请注意，我们在中添加了一条线， `return` 以便在控制台中打印带有函数（ `Message` ） [

此运算 (`TestBellState`) 将循环执行 `count` 迭代，在量子位上设置指定的 `initial` 值，然后对结果进行度量 (`M`)。 它将收集我们所度量的 0 和 1 的个数统计信息，并将其返回给调用方。 它执行另一个必需的运算。 它将量子位重置为已知状态 (`Zero`)，然后将其返回，使其他人可以在已知状态下分配此量子位。 这是 `using` 语句所必需的。

#### <a name="about-variables-in-q"></a>关于 Q 中的变量\#

默认情况下，Q# 中的变量是不可变的；它们的值在绑定后将不能更改。 `let` 关键字用于指示不可变变量的绑定。 运算参数始终是不可变的。

如果需要可以更改值的变量（如示例中的 `numOnes`），可以使用 `mutable` 关键字声明该变量。 使用 `setQubitState` 语句可以更改可变变量的值。

在这两种情况下，编译器都会推断变量的类型。 Q# 不需要为变量提供任何类型批注。

#### <a name="about-using-statements-in-q"></a>`using`问答中的语句\#

Q# 中的 `using` 语句也很特殊。 它用于分配要在代码块中使用的量子位。 在 Q# 中，所有量子位都是动态分配和释放的，而不是在复杂算法的整个生命周期内都存在的固定资源。 `using` 语句在代码块的开头分配一组量子位，并在代码块的末尾释放这些量子位。

## <a name="execute-the-code-from-the-command-line"></a>从命令行执行代码

若要运行代码，我们需要指定在提供命令时要*运行的可调用的*编译器 `dotnet run` 。 这是通过在 Q # 文件中添加一行，在此示例中添加一行，并将其 `@EntryPoint()` 直接添加到可调用： `TestBellState` 操作。 完整的代码应为：

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

若要运行程序，我们需要 `count` `initial` 从命令行指定和参数。 选择例如 `count = 1000` 和 `initial = One` 。 输入以下命令：

```dotnetcli
dotnet run --count 1000 --initial One
```

你应看到以下输出：

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

如果尝试执行此 `initial = Zero` 操作，应注意：

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>准备叠加

现在让我们看看 Q # 如何表达将 qubits 置于 superposition 的方法。  回想一下，量子位的状态可以是 0 和 1 的叠加。  为了实现这种叠加，我们将使用 `Hadamard` 操作。 如果量子位处于任一经典状态（度量始终返回 `Zero` 或始终返回 `One`），则 `Hadamard`（简称 `H`）操作会将量子位置于这样一种状态：对量子位进行度量时，50% 的情况下会返回 `Zero`，50% 的情况下会返回 `One`。  从概念上讲，可以将此量子位视为介于 `Zero` 和 `One` 之间的一种中间状态。  现在，我们在模拟 `TestBellState` 操作时会看到度量后的结果会大致返回相等数量的 `Zero` 和 `One`。  

### <a name="x-flips-qubit-state"></a>`X`翻转 qubit 状态

首先，我们来尝试翻转量子位（如果量子位为 `Zero` 状态，则会翻转为 `One`，反之亦然）。 操作步骤：先执行 `X` 操作，然后在 `TestBellState` 操作中度量它：

```qsharp
X(qubit);
let res = M(qubit);
```

现在会反转结果：

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

现在，让我们探索 qubits 的量程属性。

### <a name="h-prepares-superposition"></a>`H`准备 superposition

我们需要做的就是将上一个运行中的 `X` 操作替换为 `H`（全称为 Hadamard）操作。 我们不会将所有量子位都从 0 翻转到 1，而是只翻转一半。 `TestBellState` 中的替换行现在如下所示：

```qsharp
H(qubit);
let res = M(qubit);
```

现在，结果变得更加有趣：

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

每次度量状态时，我们都会请求一个经典值，但量子位的 0 和 1 值各占一半，因此从统计学角度而言，我们得到的 0 和 1 各占一半。
这称为“叠加”，它让我们对量子状态有了一个初步的认识。

## <a name="prepare-entanglement"></a>准备展示纠缠

现在，让我们看看 Q# 如何表达纠缠量子位的方式。
首先，我们将第一个量子位设置为初始状态，然后使用 `H` 操作将其置于叠加状态。  然后，在度量第一个 qubit 之前，我们使用新的操作（ `CNOT` ），该操作代表 "受控-NOT"。  对两个量子位执行此操作的结果是，在第一个量子位是 `One` 的情况下翻转第二个量子位。  现在，这两个量子位纠缠在一起。  第一个量子位的统计信息没有变化（在度量后，`Zero` 和 `One` 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同。 `CNOT` 把这两个量子位纠缠在了一起，因此，不论其中一个发生什么，另一个也会同样发生。 如果翻转度量值（先翻转第二个量子位，再翻转第一个），会发生相同的情况。 第一个度量值是随机的，第二个将与第一个同步。

我们需要做的第一件事就是在中分配两个 qubits，而不是一个 `TestBellState` ：

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

在这种情况下，我们可以先添加一个新操作 (`CNOT`)，再在 `TestBellState` 中度量 (`M`)：

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

我们还添加了另一个 `SetQubitState` 运算，用于初始化第一个量子位，以确保启动时它始终处于 `Zero` 状态。

我们还需要重置第二个量子位，然后再将其释放。

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

完整的例程现在如下所示：

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

新的返回值 (`agree`) 会跟踪第一个量子位的度量值与第二个量子位的度量值相同的次数。

运行我们获得的代码：

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

如概述中所述，第一个量子位的统计信息没有变化（0 和 1 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同，因为这两个量子位已纠缠在一起！

## <a name="next-steps"></a>后续步骤

[Grover 搜索](xref:microsoft.quantum.quickstarts.search)教程介绍了如何生成并运行 Grover 搜索（最常用的量子计算算法之一），并通过一个很好的 Q# 程序示例演示了如何使用量子计算来解决实际问题。  

[量子开发工具包入门](xref:microsoft.quantum.welcome)建议了更多的学习 Q# 和量子编程的方法。
