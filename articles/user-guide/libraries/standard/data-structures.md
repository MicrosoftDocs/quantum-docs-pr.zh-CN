---
title: 标准库中的数据结构 Q#
description: 了解 Microsoft 标准库中的数据结构、oracles 和 dynamical 生成器 Q# 。
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: e9b593ba69ed41a9fb3c1298b5b945a4cbe43d5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858334"
---
# <a name="data-structures-and-modeling"></a>数据结构和建模 #

## <a name="classical-data-structures"></a>传统数据结构 ##

除了用于表示量程概念的用户定义类型外，canon 还提供了操作、函数和类型，以便使用在量程系统控制中使用的传统数据。
例如， <xref:Microsoft.Quantum.Arrays.Reversed> 函数使用数组作为输入，并以相反顺序返回相同的数组。
然后，可在类型为的数组中使用 `Qubit[]` ，以避免在整数的量程表示形式之间进行转换时，无需应用不必要的 $ \operatorname{SWAP} $ 入口。
同样，我们在上一节中看到，窗体类型 `(Int, Int -> T)` 可用于表示随机访问集合，因此该 <xref:Microsoft.Quantum.Arrays.LookupFunction> 函数提供了一种从数组类型中构造此类类型的便利方法。

### <a name="pairs"></a>对 ###

Canon 支持对的函数样式表示法，由析构访问元组的补充：

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>数组 ###

Canon 提供了若干用于操作数组的函数。
这些函数是类型参数化的，因此可用于任何类型的数组 Q# 。
例如， <xref:Microsoft.Quantum.Arrays.Reversed> 函数返回一个新数组，其元素与输入的顺序相反。
这可用于更改调用操作时量程寄存器的表示方式：

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

同样，该 <xref:Microsoft.Quantum.Arrays.Subarray> 函数可用于重新排序或获取数组中元素的子集：

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

与流控制结合使用时，数组操作函数（如） <xref:Microsoft.Quantum.Arrays.Zipped> 可提供一种强大的方法来表示量程程序：

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zipped([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracles ##

在 [阶段估算](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) 和 [振幅放大](https://en.wikipedia.org/wiki/Amplitude_amplification) 文献中，oracle 的概念经常显示。
此处的术语 "oracle" 指的是一个用于处理一组 qubits 的量程子例程，并以阶段形式返回答案。
通常，可以将此子例程视为接受 oracle 的量程算法的输入，以及其他一些参数，并应用一系列的量程操作，并将对此量程子例程的调用视为一个基本入口。
很明显，若要实际实现更大的算法，必须提供 oracle 到基本入口的具体分解，但这种情况下无需进行此类分解即可了解调用 oracle 的算法。
在中 Q# ，此抽象通过使用该操作是第一类值来表示，这样，就可以将操作以黑白方式传递到量程算法的实现中。
此外，用户定义的类型用于以类型安全的方式标记不同的 oracle 表示形式，这使得难以偶然人们常常会不同种类的黑框操作。

此类 oracles 显示在多个不同的上下文中，其中包括 [Grover 的搜索](https://en.wikipedia.org/wiki/Grover%27s_algorithm) 和量程模拟算法等著名示例。
这里，我们将重点介绍两个应用程序所需的 oracles：振幅放大和相位估算。
首先，我们将讨论振幅放大 oracles，然后再继续进行阶段估算。

### <a name="amplitude-amplification-oracles"></a>振幅放大 Oracles ###

振幅放大算法旨在通过应用一系列状态反射来执行初始状态和最终状态之间的旋转。
为了使算法正常工作，需要对这两种状态进行规范。
这些规范由两个 oracles 提供。
这些 oracles 的工作原理是将输入分为两个空格： "target" 子空间和 "初始" 子空间。
Oracles 标识了这样的 subspaces，与 Pauli 运算符如何识别两个空格的方式类似，通过将 $ \pm $1 阶段应用于这些空格。
主要区别在于，在此应用程序中，这些空间不必为半空格。
另请注意，这两个 subspaces 通常不是互斥的：这两个类型的向量都是两个空格的成员。
如果不是这样，则幅度放大将不会产生任何影响，因此我们需要初始子空间与目标子空间不为零重叠。

我们将表示我们需要将振幅放大的第一台 oracle 用于 $P \_ $0，定义为执行以下操作。  对于 "初始" 子空间中的所有状态 $ \ket{x} $ $P \_ 0 \ket{x} =-\ket{x} $ 和不在此 \ket{y} 中的所有状态 $ 子空间 $，我们 $P \_ 0 \ket{y} = \ket{y} $。
标记目标子空间 $P _1 $ 的 oracle 将采用完全相同的形式。
对于目标子空间中的所有状态 $ \ket{x} $ (即，对于想要算法输出) 的所有状态，$P _1 \ 票证 {x} =-\ket{x} $。
同样，对于不在目标子空间中的所有状态 $ \ket{y} $ $P _1 \ 票证 {y} = \ket{y} $。
然后将这两个反射组合起来以形成一个运算符，该运算符将制定 =-P_0 P_1 $ 的单个步骤 $Q，其中，整体减号只是在受控应用程序中考虑。
然后，振幅放大进入初始状态的 $ \ket{\psi} $，然后执行 $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $。
执行此类迭代可保证如果一次启动时使用的初始状态与已标记的空格重叠 $ \sin ^ 2 ( \theta) $，则 $m $ 迭代后，此重叠将变为 $ \sin ^ 2 ( [2m + 1] \theta) $。
因此，我们通常希望选择 $m $ 为自由参数，如 $ [2m + 1] \theta = \ pi/2 $;但是，这种严格的选择对于某些形式的振幅放大（如固定点波幅放大）并不重要。
使用此过程，我们可以在标记的子空间中准备一个状态，使用几率更少查询标记函数，将状态准备函数限制在严格的设备上。
这就是为什么在量程计算的许多应用程序中，振幅放大是一个重要的构建基块。

若要了解如何使用该算法，提供一个提供 oracles 构造的示例非常有用。  请考虑在此设置中执行 Grover 的数据库搜索算法。
在 Grover 的搜索中，目标是将状态 $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket $ 转换为 {0} (之一可能) 多个标记的状态。
为了进一步简化，只需查看标记状态为 $ \ket $ 的情况 {0} 。
接下来，我们设计了两个 oracles：一个仅使用减号标记初始状态 $ \ket{+} ^ {\otimes n} $，另一个使用减号标记标记状态 $ \ket {0} $。
通过使用 canon 中的控制流操作，可以使用以下处理操作来实现后一门：

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

此 oracle 是操作的一种特殊情况 <xref:Microsoft.Quantum.Canon.RAll1> ，它允许由任意阶段（而不是反射事例 $ \phi = \pi $）进行旋转。
在这种情况下， `RAll1` 类似于 <xref:Microsoft.Quantum.Intrinsic.R1> prelude 操作，因为它会旋转约 $ \ket{11\cdots1} $，而不是单 qubit 状态 $ \ket {1} $。

标记初始子空间的 oracle 可以按类似方式构造。
在伪代码中：

1. 将 $H $ 门应用到每个 qubit。
2. 将 $X $ 门应用到每个 qubit。
3. 将 $n-$1 控制的 $Z $-入口应用到 $n ^ {\text{th}} $ qubit。
4. 将 $X $ 门应用到每个 qubit。
5. 将 $H $ 门应用到每个 qubit。

这次，我们还将演示如何 <xref:Microsoft.Quantum.Canon.ApplyWith> 结合 <xref:Microsoft.Quantum.Canon.RAll1> 上述操作使用：

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

然后，可以将这两个 oracles 组合在一起，以在两个状态之间切换，并使用多个与 $ Hadamard ^ n 关联的 \Sqrt{2 入口层来确定将 $ \ket{+} ^ {\otimes n} $ 转换为 $ \ket {0} $ (ie $m \propto \sqrt{2 ^ n} $) 与大约 $ 2 ^ n $ 层之间的对比，这是因为在观察到 {0} 结果 $0 $ 之前准备和测量初始状态所需要的。

### <a name="phase-estimation-oracles"></a>阶段估算 Oracles ###

对于阶段估算，oracles 有些自然。
阶段估算中的目标是设计一个子例程，该子例程能够从单一矩阵的本征值进行抽样。
这种方法在量程模拟中是不可或缺的，因为化学和材料科学中的许多物理问题都是本征值的凝聚系统，它为我们提供有关分子的材料和反应 dynamics 的阶段示意图的重要信息。
每个阶段估计风格都需要一个输入。
这种单一方法通常由两种类型的 oracles 之一来描述。

> [!TIP]
> 示例中介绍了以下两种 oracle 类型。
> 若要了解有关连续查询 oracles 的详细信息，请参阅 [ **PhaseEstimation** 示例](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation)。
> 若要了解有关离散查询 oracles 的详细信息，请参阅 [ **IsingPhaseEstimation** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation)。

第一种类型的 oracle 是，我们称之为单独查询 oracle 并使用用户定义类型表示 <xref:Microsoft.Quantum.Oracles.DiscreteOracle> ，只涉及一个单一矩阵。
如果 $U $ 是要估计其本征值的单一项，则 $U $ 的 oracle 只是实现 $U $ 的子程序的一个独立。
例如，可以将 $U $ 指定为上述 oracle $Q $ 来估算幅度估算。
此矩阵的本征值可用于估算初始状态与目标状态之间的重叠，$ \sin ^ 2 ( \theta) $，使用的样本越少，将需要其他值。
这盈利将使用 Grover oracle $Q $ 作为输入的应用程序阶段估算作为输入的名字对象。
量程 metrology 中广泛使用的另一个常见应用程序涉及到估计一个小旋转角度。
换句话说，我们想要为窗体 $R _z ( \theta) $ 的未知旋转入口估计 $ \theta $。
在这种情况下，我们要与之交互的子例程是： $ $ \begin{align} U & = R_z ( \theta) \\ \\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ theta/2} \end{bmatrix}。
\end{align} $ $

阶段估算中使用的第二种类型的 oracle 是连续查询 oracle，由 <xref:Microsoft.Quantum.Oracles.ContinuousOracle> 类型表示。
Oracle for 阶段估算的连续查询采用 $U (t) $ 的形式，其中 $t $ 是经典的已知实数。
如果允许 $U $ 是固定的单一项，则 oracle 查询将采用 (t) = U ^ t $ $U 的格式。
这样，我们就可以查询如 $ \sqrt{U} $ 这样的矩阵，这些矩阵无法直接在离散查询模型中实现。

这种类型的 oracle 非常有用，因为你不会探测特定的单一系统，而是想要了解单一的生成器属性。
例如，在 dynamical 量程模拟中，目标是设计一些量程线路，使其大致接近 $U (t) = e ^ {-i H t} $ for Hermitian matrix $H $ 和演化时间 $t $。
$U (t) $ 的本征值直接与 $H $ 的本征值相关联。
若要查看此内容，请考虑 $H $： $H \ket{E} = E\ket {E} $ 的 eigenvector，然后可以从矩阵指数的电源系列定义中轻松看出，$U (t) \ket{E} = e ^ {i\phi} \ 票证} iEt $。
因此，若要估计 $U (t) $ 的 eigenphase，请将 eigenvalue $E $ 假设 eigenvector $ \ket{E} $ 输入到阶段估算算法中。
但是，在这种情况下，可以按用户的意愿选择值 $t $，因为 $t $ 的任何足够小值都可以通过 $E =-\ phi/t $ $E 唯一反转。
由于量程模拟方法提供执行小数演变的功能，因此，在查询单一阶段时，这会授予阶段估算算法额外的自由度，具体而言，在离散查询模型只允许使用 $U ^ j $ 形式为 integer $j $ 的形式的 unitaries 时，可以使用 "持续查询" 来将 ^ t $t $ $U ^ t $ 的形式近似于 "unitaries"。
这一点非常重要，因为它使我们能够精确地选择可提供有关 $E $ 的最多信息的试验：而基于离散查询的方法必须在算法中选择最大的整数查询来使其成为损害。

作为此问题的具体示例，请考虑估计不是门的旋转角度但旋转后的量程系统的 procession 频率的问题。
描述此类量程动态的单一 $U (t) = R_z (2 \ omega t) $，以获取演化时间 $t $ 和 unknown frequency $ \omega $。
在这种情况下，我们可以使用单个 $R $ 关口来模拟任何 $t $ $U (t) $，因此，不需要将自己限制为仅限单一的单独查询。
此类连续模型还具有属性，该属性可以从使用连续查询的阶段估算流程中了解到 $ 2 \ pi $ 的频率，这是因为在相当 $ 的非 $t 值上执行的试验结果可能会显示通过对数函数的分支切口来屏蔽的阶段信息。
因此，对于这样的问题，例如，针对阶段估计 oracle 的连续查询模型不仅合适，而且还优于离散查询模型。
出于此原因，对于 Q# 这两种形式的查询都具有功能，并将其留给用户，以决定满足其需求的阶段估算算法，以及可用的 oracle 类型。

## <a name="dynamical-generator-modeling"></a>Dynamical 生成器建模 ##

时间演化的生成器介绍状态随着时间推移的发展方式。 例如，量程状态 $ \ket{\psi} $ 的 dynamics 由 Schrödinger 公式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = H \ket{\psi (t) }，\end{align} $ $ 和 Hermitian matrix $H $ （称为 Hamiltonian，作为运动的生成器。 给定初始状态 $ \ket{\psi (0) } $，时间 $t = $0，这种情况下，此公式的正式解决方案 $t $ 可能是按以下方式编写的： $ $ \begin{align} \ket{\psi (t) } = U (t) \ket{\psi (0) }，\end{align} $ $，其中矩阵指数 $U (t) = e ^ {-i H t} $ 称为单一时间演化运算符。 尽管我们将重点放在下面这一窗体的发电机上，但我们强调到，该概念更广泛地应用，例如模拟开放的量程系统或更多抽象的差分等式。

Dynamical 模拟的主要目标是对在量程计算机的 qubits 中编码的某些量程状态实施时间演化运算符。  在许多情况下，Hamiltonian 可能会被分解为某些 $d $ 简化术语的总和

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j，\end{align} $ $

在量程计算机上，每个术语单独进行的时间演化非常容易实现。 例如，如果 $H _j $ 是一个在 qubit 寄存器的第一个和第二个元素上执行的 Pauli $X _1X_2 $ operator `qubits` ，则它在任何时间 $t $ 只能通过调用具有签名的操作来实现 `Exp([PauliX,PauliX], t, qubits[1..2])` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。 如稍后在 Hamiltonian 模拟中所述，一个解决方案是通过使用一系列简单的操作 $H $ 来估算时间演变。

$ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/r} e ^ {-iH \_ 1 t/r} \cdots e ^ {-iH \_ {d} \right) d ^ 2 \ (\\ |H \_ j \\ | ^ 2 t ^ 2/r) ，\end{align} $ $

其中整数 $r > $0 控制近似值错误。

Dynamical 生成器建模库提供了一个框架，用于在更简单的生成器方面系统地编码复杂的生成器。 然后，可以通过所选的模拟算法将此类描述传递给模拟库，以实现由所选模拟算法进行的时间演化，并自动处理许多详细信息。

> [!TIP]
> 示例中介绍了下面描述的 dynamical 生成器库。 有关基于 Ising 模型的示例，请参阅 [ **IsingGenerators** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators)。
> 有关基于分子 Hydrogen 的示例，请参阅 [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) 和 [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui) 示例。

### <a name="complete-description-of-a-generator"></a>生成器的完整说明 ###

在顶级，包含 `EvolutionGenerator` 两个组件的用户定义类型中包含了 Hamiltonian 的完整描述。：

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

`GeneratorSystem`用户定义类型是 Hamiltonian 的传统说明。

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

元组的第一个元素将 Hamiltonian 中的 `Int` $d 字词数量存储在中，第二个元素 `(Int -> GeneratorIndex)` 是一个函数，该函数将 1,..., 的整数索引映射 \{ \} 到一个 `GeneratorIndex` 用户定义的类型，该类型在 Hamiltonian 中唯一标识每个基元术语。 请注意，通过将 Hamiltonian 中的字词集合表示为函数（而不是数组 `GeneratorIndex[]` ），这可以实现的即时计算， `GeneratorIndex` 这在描述包含大量字词的 Hamiltonians 时特别有用。

至关重要，我们不会对由标识的基元术语进行简单的约定 `GeneratorIndex` 。 例如，基元术语可能是 Pauli 运算符，如前文所述，但也可以是 Fermionic annihilation 和创建运算符，通常用于量程化学模拟。 它本身并 `GeneratorIndex` 无意义，因为它不会描述它所指向的字词的时间演变如何作为一个量子线路来实现。

这可通过以下方式解决：指定一个 `EvolutionSet` 用户定义的类型，该类型将 `GeneratorIndex` 从某个规范集绘制的任何映射到一个单一运算符（ `EvolutionUnitary` 表示为一个量子线路）。 `EvolutionSet`定义 `GeneratorIndex` 结构的构造方式，并且还定义了一组可能的 `GeneratorIndex` 。

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Pauli 运算符生成器 ###

生成器的一个具体和有用的示例是 Hamiltonians，它们都是 Pauli 运算符的总和，每个都可能使用不同的系数。
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j，\end{align} $ $，其中每个 $ \hat H_j $ 现在都是从 Pauli 组中提取的。 对于这类系统，我们提供类型为的，用于 `PauliEvolutionSet()` `EvolutionSet` 定义 Pauli 组的元素和系数如何由标识 `GeneratorIndex` （具有以下签名）的约定。

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

在编码中，第一个参数 `Int[]` 指定 Pauli 字符串，其中 $ \Hat I\rightarrow $0，$ \Hat X\rightarrow $1，$ \Hat Y\rightarrow $2，$ \Hat Z\rightarrow $3。 第二个参数将 `Double[]` Pauli 字符串的系数存储在 Hamiltonian 中。 请注意，只使用此数组的第一个元素。 第三个参数 `Int[]` 将对此 Pauli 字符串处理的 qubits 进行索引，并且必须没有重复元素。 因此，Hamiltonian 术语 $0.4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ 可以表示为

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()`是一个函数，它将 `GeneratorIndex` 此窗体的任何映射到 `EvolutionUnitary` 具有以下签名的。

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

第一个参数表示一个时间段，此时间段将乘以单一演变的中的系数 `GeneratorIndex` 。 第二个参数是 qubit register 单一操作。 

### <a name="time-dependent-generators"></a>Time-Dependent 生成器 ###

在许多情况下，我们还对与时间相关的生成器进行建模，Schrödinger 公式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = \hat H (t) \ket{\psi (t) }，\end{align} $ $，其中生成器 $ \hat H () $ 现在取决于时间。 这种情况下，与此案例相关的独立生成器的扩展非常简单。 不是将 `GeneratorSystem` Hamiltonian 的所有 $t 时间都固定在一起，而是使用 `GeneratorSystemTimeDependent` 用户定义的类型。

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

第一个参数是连续的 schedule 参数 $s \in [0，1] $，而此类型的函数返回 `GeneratorSystem` 该计划的。 请注意，计划参数可能与物理时间参数（例如 $s = t/T $）线性相关，以表示模拟的总时间 $T $。 但一般情况下不需要这样做。

同样，此生成器的完整说明需要 `EvolutionSet` ，因此我们定义 `EvolutionSchedule` 用户定义类型。

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
