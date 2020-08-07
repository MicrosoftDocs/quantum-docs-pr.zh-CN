---
title: 探索牵连Q#
description: 了解如何在中编写量程计划 Q# 。 使用 Quantum 开发工具包 (QDK) 开发 Bell 态应用程序
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: c66d26b5ea253d6fc2633fbe52fa35ba703d185d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869692"
---
# <a name="tutorial-explore-entanglement-with-q"></a>教程：通过 Q\# 探索纠缠

在本教程中，我们将向您展示如何编写操作 Q# 和测量 qubits 的程序，并演示 superposition 和牵连的影响。

我们将编写一个用于演示量子纠缠的名为 Bell 的应用程序。
Bell 这一名称是指 Bell 状态，即两个量子位的特定量子状态，用于表示叠加和量子纠缠的最简单示例。

## <a name="pre-requisites"></a>先决条件

如果准备开始编码，请在继续之前按照以下步骤操作： 

* 使用你首选的语言和开发环境[安装](xref:microsoft.quantum.install)量程开发工具包。
* 如果已安装 QDK，请确保将其[更新](xref:microsoft.quantum.update)至最新版本

你还可以遵循这些叙述，无需安装 QDK、查看 Q# 编程语言的概述以及量程计算的第一概念。

## <a name="in-this-tutorial-youll-learn-how-to"></a>在本教程中，你将学习如何执行以下操作：

> [!div class="checklist"]
> * 在 Q 中创建和合并操作\#
> * 创建操作，将 qubits 置于 superposition、entangle 中并度量它们。
> * 演示 Q# 在模拟器中运行的程序的量程牵连。 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>通过 QDK 演示 qubit 行为

经典位保存单个二进制值（如 0 或 1），而[量子位](xref:microsoft.quantum.glossary#qubit)的状态则可以是 0 和 1 的**叠加**。  从概念上讲，qubit 的状态可以看作是抽象空间中的方向 (也称为矢量) 。  Qubit 状态可以为任何可能的方向。 两个**经典状态**是两个方向，一个方向表示度量结果为 0 的可能性为 100%，另一个方向表示度量结果为 1 的可能性为 100%。

度量行为会生成二进制结果并改变量子位状态。
度量值生成一个二进制值，0或1。  量子位从叠加态（任何方向）变为经典状态之一。  随后，在没有任何干预操作的情况下重复进行相同的度量会生成相同的二进制结果。  

多个量子位可以[**纠缠**](xref:microsoft.quantum.glossary#entanglement)在一起。  度量一个纠缠的量子位时，就会知道另一个量子位的状态。

现在，我们已准备好演示如何 Q# 表达这一行为。  一开始可以编写并生成一个最简单的程序，用于演示量子叠加和量子纠缠。

## <a name="creating-a-no-locq-project"></a>创建 Q# 项目

首先，我们要做的就是创建一个新 Q# 项目。 在本教程中，我们将使用基于[命令行应用程序 VS Code](xref:microsoft.quantum.install.standalone)的环境。

若要创建新项目，请在 VS Code 中： 

1. 单击 "**查看**" "  ->  **命令面板**"，然后选择 " ** Q# 创建新项目**"。
2. 单击“独立控制台应用程序”。
3. 导航到项目的保存位置，然后单击“创建项目”。
4. 成功创建项目后，单击右下方的“打开新项目…”。

在此示例中，我们调用了项目 `Bell` 。 这会生成两个文件： `Bell.csproj` 、项目文件和 `Program.qs` ，这是 Q# 我们将用于编写应用程序的应用程序模板。 的内容 `Program.qs` 应为：

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
 
我们的目标是在特定的量程状态下准备两个 qubits，演示如何在 qubits 上操作 Q# 以更改其状态，并演示 superposition 和牵连的效果。 我们将构建这一段内容，以引入 qubit 状态、操作和度量。

### <a name="initialize-qubit-using-measurement"></a>使用度量值初始化 qubit

下面的第一个代码介绍了如何在中使用 qubits Q# 。  我们将介绍两个操作，这些操作将 [`M`](xref:microsoft.quantum.intrinsic.m) [`X`](xref:microsoft.quantum.intrinsic.x) 转换 qubit 的状态。 在此代码片段中，我们定义了操作 `SetQubitState`。该操作使用一个量子位作为参数，使用另一个参数 (`desired`) 来表示我们希望该量子位呈现的状态。  操作 `SetQubitState` 使用操作 `M` 对量子位进行度量。  在中 Q# ，qubit 度量值始终返回 `Zero` 或 `One` 。  如果度量值返回一个不等于所需值的值，则 `SetQubitState` "翻转" qubit; 也就是说，它将执行一个 `X` 操作，该操作会将 qubit 状态更改为一种新状态，在该状态下，测量的概率返回 `Zero` 并 `One` 反转。 这样，就 `SetQubitState` 始终将目标 qubit 置于所需状态。

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

#### <a name="about-no-locq-operations"></a>关于 Q# 操作

Q#操作是一个量程子例程。 也就是说，它是包含对其他量程操作的调用的可调用例程。

运算的参数在括号内指定为元组。

运算的返回类型在冒号之后指定。 根据这个规则，`SetQubitState` 运算表示没有返回类型，因此将标记为返回 `Unit`。 这是 Q# `unit` F # 中的等效项，它大致类似于 `void` c # 中的，空元组 (`Tuple[()]` 在 Python 中) 。

您在第一次操作中使用了两个量程操作 Q# ：

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
请注意，我们在中添加了一条线， `return` 以便在控制台中打印一条说明性消息，其中包含函数 (`Message`) []

此运算 (`TestBellState`) 将循环执行 `count` 迭代，在量子位上设置指定的 `initial` 值，然后对结果进行度量 (`M`)。 它将收集我们所度量的 0 和 1 的个数统计信息，并将其返回给调用方。 它执行另一个必需的运算。 它将量子位重置为已知状态 (`Zero`)，然后将其返回，使其他人可以在已知状态下分配此量子位。 这是 `using` 语句所必需的。

#### <a name="about-variables-in-q"></a>关于 Q 中的变量\#

默认情况下，中的变量 Q# 是不可变的; 它们的值在绑定后可能不会更改。 `let` 关键字用于指示不可变变量的绑定。 运算参数始终是不可变的。

如果需要可以更改值的变量（如示例中的 `numOnes`），可以使用 `mutable` 关键字声明该变量。 使用 `setQubitState` 语句可以更改可变变量的值。

在这两种情况下，编译器都会推断变量的类型。 Q#不需要任何变量的类型批注。

#### <a name="about-using-statements-in-q"></a>`using`问答中的语句\#

`using`语句也是特殊的 Q# 。 它用于分配要在代码块中使用的量子位。 在中 Q# ，所有 qubits 都是动态分配和释放的，而不是固定在复杂算法的整个生存期内的资源。 `using` 语句在代码块的开头分配一组量子位，并在代码块的末尾释放这些量子位。

## <a name="execute-the-code-from-the-command-line"></a>从命令行执行代码

若要运行代码，我们需要指定在提供命令时要*运行的可调用的*编译器 `dotnet run` 。 此操作 Q# 通过在此情况下添加一行，并在 `@EntryPoint()` `TestBellState` 此示例中添加一行，在文件中进行简单的更改。 完整的代码应为：

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

现在让我们看看如何 Q# 在 superposition 中表达 qubits 的方式。  回想一下，量子位的状态可以是 0 和 1 的叠加。  为了实现这种叠加，我们将使用 `Hadamard` 操作。 如果量子位处于任一经典状态（度量始终返回 `Zero` 或始终返回 `One`），则 `Hadamard`（简称 `H`）操作会将量子位置于这样一种状态：对量子位进行度量时，50% 的情况下会返回 `Zero`，50% 的情况下会返回 `One`。  从概念上讲，可以将此量子位视为介于 `Zero` 和 `One` 之间的一种中间状态。  现在，我们在模拟 `TestBellState` 操作时会看到度量后的结果会大致返回相等数量的 `Zero` 和 `One`。  

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

现在让我们看看如何 Q# 表达 entangle qubits 的方法。
首先，我们将第一个量子位设置为初始状态，然后使用 `H` 操作将其置于叠加状态。  然后，在度量第一个 qubit 之前，我们使用 () 的新操作 `CNOT` ，该操作代表受控-NOT。  对两个量子位执行此操作的结果是，在第一个量子位是 `One` 的情况下翻转第二个量子位。  现在，这两个量子位纠缠在一起。  第一个量子位的统计信息没有变化（在度量后，`Zero` 和 `One` 各一半），但现在当我们度量第二个量子位时，它__始终__与我们第一个量子位的度量值相同。 `CNOT` 把这两个量子位纠缠在了一起，因此，不论其中一个发生什么，另一个也会同样发生。 如果翻转度量值（先翻转第二个量子位，再翻转第一个），会发生相同的情况。 第一个度量值是随机的，第二个将与第一个同步。

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

教程[Grover 的搜索](xref:microsoft.quantum.quickstarts.search)介绍了如何生成和运行 Grover 搜索，这是最常用的一种量程计算算法，提供了一个 Q# 可用于解决量程计算的真正问题的程序示例。  

[量程开发工具包入门建议了](xref:microsoft.quantum.welcome)更多学习 Q# 和量程编程的方法。
