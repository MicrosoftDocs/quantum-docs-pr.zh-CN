---
title: 'Q # 标准库中的诊断'
description: '了解用于在量程程序中捕获错误或错误的 Q # 标准库中的诊断功能和操作。'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: ba2f248327bb3db4ee895f8e65ea31c17e42b5f4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906230"
---
# <a name="diagnostics"></a>诊断 #

与传统开发一样，能够在量程程序中诊断错误和错误非常重要。
Q # 标准库提供了各种不同的方法来确保量程程序的正确性，如 <xref:microsoft.quantum.techniques.testing-and-debugging>中所述。
在很大程度上说，这种支持是函数和操作的形式，它们指示目标计算机向宿主程序或开发人员提供额外的诊断信息，或强制执行所表示的条件和固定条件的正确性通过函数或操作调用。

## <a name="machine-diagnostics"></a>计算机诊断 ##

可以通过使用 <xref:microsoft.quantum.intrinsic.message> 函数以计算机相关的方式记录消息，从而获取有关传统值的诊断。
默认情况下，这会将字符串写入控制台。
与内插字符串一起使用时，<xref:microsoft.quantum.intrinsic.message> 可以轻松地报告有关传统值的诊断信息：

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` 具有签名 `(String -> Unit)`，则无法从 Q # 内观察发出调试日志消息的。

<xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister> callables 指示目标计算机提供有关当前已分配的所有 qubits 的诊断信息，或分别提供有关 qubits 的特定寄存器的诊断信息。
每个目标计算机因提供的诊断信息而异，以响应转储指令。
例如，[完整状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)目标虚拟机为主机程序提供了其内部使用的状态向量，以表示寄存器 qubits。
相比之下， [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)目标计算机为每个 qubit 提供一个传统位。

 若要详细了解[完整状态模拟器的](xref:microsoft.quantum.machines.full-state-simulator)`DumpMachine` 输出，请参阅我们的[测试和调试一文](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions)的 "转储函数" 一节。


## <a name="facts-and-assertions"></a>事实和断言 ##

如[测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)中所述，可以将签名 `Unit -> Unit` 或 `Unit => Unit`的函数或操作分别标记为*单元测试*。
每个单元测试通常包含一个小型量程计划，以及一个或多个检查该程序的正确性的条件。
这些条件可采用以下两种形式之一：检查输入的值或_断言_，这些_事实_检查作为输入传递的一个或多个 qubits 的状态。

例如，`EqualityFactI(1 + 1, 2, "1 + 1 != 2")` 表示 $1 + 1 = $2 的数学事实，而 `AssertQubit(One, qubit)` 表示衡量 `qubit` 将以确定性返回 `One` 的条件。
在前一种情况下，我们可以检查只给定其值的条件的正确性，而在后一种情况下，我们必须知道 qubit 的状态，以便评估断言。

Q # 标准库提供了若干不同的函数来表示事实，其中包括：

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>测试 Qubit 状态 ###

实际上，断言依赖于这一事实，即，对量子机制的传统模拟不需要遵循非[克隆定理](https://arxiv.org/abs/quant-ph/9607018)，因此，我们可以在为目标计算机使用模拟器时进行 unphysical 测量和断言。
因此，可以在部署硬件之前，在传统模拟器上测试各个操作。
在不允许评估断言的目标计算机上，可以安全地忽略对 <xref:microsoft.quantum.intrinsic.assert> 的调用。

更常见的情况是，<xref:microsoft.quantum.intrinsic.assert> 运算断言，测量给定 Pauli 基础中的给定 qubits 将始终具有给定的结果。
如果断言失败，则将通过使用给定的消息调用 `fail` 结束执行。
默认情况下，不实现此操作;可支持它的模拟器应该提供执行运行时检查的实现。
`Assert` 具有 `((Pauli[], Qubit[], Result, String) -> ())`签名。
由于 `Assert` 是一种将空元组作为其输出类型的函数，因此，不会有调用 `Assert` 的影响在 Q # 程序中是显而易见的。

在某种程度上，<xref:microsoft.quantum.intrinsic.assertprob> 操作函数断言，该函数在给定的 Pauli 基础上测量给定的 qubits，以给定的概率表示给定的结果。
容差为累加（例如 `abs(expected-actual) < tol`）。
如果断言失败，则将通过使用给定的消息调用 `fail` 结束执行。
默认情况下，不实现此操作;可支持它的模拟器应该提供执行运行时检查的实现。
`AssertProb` 具有 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`签名。 `Double` 的第一个参数提供所需的结果概率，第二个参数提供公差。

我们不仅可以使用断言单个度量值，还可以使用模拟器用来表示 qubit 的内部状态的传统信息适合复制，这样我们就不需要实际执行度量来测试断言。
具体而言，这使我们能够考虑到在实际硬件上无法进行的*不兼容*指标。

假定 `P : Qubit => Unit` 是一项操作，用于在其输入处于状态 $ \ket{0}$ 时准备状态 $ \ket{\psi} $。
让 $ \ket{\psi '} $ 是 `P`准备的实际状态。
然后，当且仅当 $ \ket{\psi} $ 描述的轴中的 $ \ket{\psi '} $ 度量 $ '} $ 时，$ \ket{\psi} = \ket{\psi '} $ 总是返回 `Zero`。
也就是说，如果且仅当} \braket{\psi | \psi '} = 1 时，\begin{align} \ket{\psi} = \ket{\psi '} \text{。
\end{align} 使用在 prelude 中定义的基元运算，可以直接执行一个度量值，该度量值将在 $ \ket{\psi} $ eigenstate 为 Pauli 运算符之一时返回 `Zero`。


如果要测试断言 $ \ket{\psi} = \ket{0}$，操作 <xref:microsoft.quantum.diagnostics.assertqubit> 提供了一个特别有用的速记。
这种情况很常见，例如，当我们 uncomputed 将 ancilla qubits 返回到 ${0}\ket 后，再将其释放。
如果希望断言两种状态准备 `P` 和 `Q` 操作都准备相同的状态，并且 `Q` 支持 `Adjoint`，则对 $ \ket{0}$ 进行断言也很有用。
特别是，

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

但是，更常见的情况是，我们无法访问断言与 Pauli 运算符的 eigenstates 不一致的状态。
例如，$ \ket{\psi} = （\ket{0} + e ^ {i \pi/8} \ket{1}）/\sqrt{2}$ 不是任何 Eigenstate 运算符的 Pauli，因此不能使用 <xref:microsoft.quantum.intrinsic.assertprob> 来唯一确定状态 $ \ket{\psi '} $ 等于 $ \ket{\psi} $。
相反，我们必须将断言 $ \ket{\psi '} = \ket{\psi} $ 分解为可使用模拟器支持的基元直接测试的假设。
为此，请让 $ \ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ 用于复数 $ \alpha = a\_r + a\_i $ 和 $ \beta $。
请注意，此表达式需要四个实数 $\{一个\_r、一个\_i、b\_r、b\_i\}$ 来指定，因为每个复数都可以表示为实部和虚部的总和。
不过，由于全局阶段，我们可以选择 $a\_i = $0，因此，我们只需三个实数即可唯一指定 qubit 状态。

因此，需要指定三个断言，它们彼此独立，以便断言所需的状态。
为此，我们需要查找每个 Pauli 度量值（给定 $ \alpha $ 和 $ \beta $）的观察 `Zero` 的概率，并分别对每个度量值进行断言。
让 $x $、$y $ 和 $z $ 分别 `Result` 值 $X $、$Y $ 和 $Z $ 度量值。
然后，对量程度量值使用可能性函数 \begin{align} \Pr （x = \texttt{Zero} | \alpha，\beta） & = \frac12 + a\_r b\_r + a\_i b\_\\\\ \Pr （y = \texttt{Zero} | \alpha，\beta） & = \frac12 + a\_r b\_\Pr i b\_r \\\\ （z = \texttt{Zero} | \alpha，\beta） & = \frac12\left （1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_\_i ^ 2 \right）。
\end{align}

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 操作以 <xref:microsoft.quantum.math.complex>类型的值的形式实现了 $ \alpha $ 和 $ \beta $ 表示形式的这些断言。
当预期状态可数学计算时，这非常有用。

### <a name="asserting-equality-of-quantum-operations"></a>断言量程运算的相等性 ###

到目前为止，我们关注的是用于准备特定状态的测试操作。
不过，通常情况下，我们对操作如何处理任意输入（而不是单个固定的输入）感兴趣。
例如，假设我们已实现了一个操作 `U : ((Double, Qubit[]) => () : Adjoint)` 对应于一系列 $U （t） $ 的单一运算符，并且提供了显式 `adjoint` 块，而不是使用 `adjoint auto`。
如果 $t $ 表示演化时间，我们可能会有兴趣断言 $U ^ \dagger （t） = U （-t） $。

广泛地说，我们可以遵循两种不同的策略，使断言指出两个操作 `U`，`V` 的行为相同。
首先，我们可以检查 `U(target); (Adjoint V)(target);` 在给定的基础上保留每种状态。
其次，我们可以检查 `U(target); (Adjoint V)(target);` 在放大状态的一半上是否保留了牵连。
这些策略由 canon 操作分别实现 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> 和 <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>。

> [!NOTE]
> 上面所述的引用断言基于[Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)，这是一个数学框架，该框架将 $n $ qubits 上的操作与 $ 2n $ 放大上的 qubits 状态关联起来。
> 具体而言，$n $ qubits 上的标识操作由放大状态 $ \ket{\ beta_{00}} \mathrel{： =} （\ket{00} + \ket{11}）/\sqrt{2}$ $n $ 个副本表示。
> 操作 <xref:microsoft.quantum.preparation.preparechoistate> 实现此 isomorphism，准备表示给定操作的状态。

大致而言，这些策略可通过时间空间平衡来区分。
循环访问每个输入状态需要额外的时间，而使用牵连作为引用需要存储其他 qubits。
如果某个操作实现可逆的传统操作，使其只对计算基础状态的行为感兴趣，则 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> 测试此限制的输入集的相等性。

> [!TIP]
> 针对输入状态的迭代由 <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> 和 <xref:microsoft.quantum.canon.iteratethroughcartesianpower>的枚举操作处理。
> 这些操作更适用于将操作应用于两个或多个集之间笛卡尔积的每个元素。

但更严重的是，这两种方法测试正在检查的操作的不同属性。
由于就地断言多次调用每个操作，因此对每个输入状态一次，任何随机选项和测量结果可能在调用之间发生变化。
与此相反，引用的断言只调用一次每个操作一次，以便*在一个拍摄中*检查操作是否相等。
这两个测试可用于确保量程程序的正确性。


## <a name="further-reading"></a>延伸阅读 ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
