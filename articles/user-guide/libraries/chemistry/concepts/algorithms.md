---
title: 模拟 Hamiltonian Dynamics
description: 了解如何使用 Trotter-Suzuki 公式和 qubitization 来处理 Hamiltonian 模拟。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: eeaa13b99ab07ce22f8a3306a756bf7ac7cde65b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857599"
---
# <a name="simulating-hamiltonian-dynamics"></a>模拟 Hamiltonian Dynamics

将 Hamiltonian 表示为基本运算符的总和后，就可以使用一系列众所周知的技术将 dynamics 编译为基本的入口操作。
有三种有效的方法，包括 Trotter – Suzuki 公式、unitaries 和 qubitization 的线性组合。
我们将介绍以下三种方法，并 Q# 举例说明如何使用 Hamiltonian 模拟库实现这些方法。


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki 公式
Trotter – Suzuki 公式背后的理念非常简单：将 Hamiltonian 表达为易于模拟 Hamiltonians，然后以这些更简单的今后的序列来估算总体演变。
具体而言，让 $H = \ sum_ {j = 1} ^ m H_j $ 为 Hamiltonian。
然后，$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2) ，$ $ 这就是，如果 $t \ll $1，则此近似值中的错误将变为可忽略的。
请注意，如果 $e ^ {-i H t} $ 是普通指数，则不会 $O 此近似值中的错误 (m ^ 2 t ^ 2) $：该值为零。
之所以发生此错误，是因为 $e ^ {-iHt} $ 是运算符指数，因此，使用此公式时出现错误，原因是 $H _j $ 词条不 *在 (的*$H _j H_k H_k H_j) $。

如果 $t $ 是大的，则仍可以使用 Trotter – Suzuki 公式来准确模拟动态，方法是将其分解为一系列简短的时间。
让 $r $ 是在时间演化过程中执行的步骤数，因此每次运行的时间 $t/r $。 接下来，我们将使用 $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left ( \ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ 右) ^ r + O (m ^ 2 t ^ 2/r) $ $ 这意味着如果 $r $ 缩放为 $m ^ 2 t ^ 2/\ epsilon $，则对于任何 $ \epsilon>$0，最多可以执行 $ \epsilon $ 此错误。

通过构造运算符指数的序列来生成更准确的近似值，使错误词取消。
最简单的此类公式，第二个顺序 Trotter-Suzuki 公式，采用格式 $ $ U_2 (t) = \left ( \ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2r} \ 右) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2) 对于任何 $ \epsilon>$0，$ $ $r $ 可扩展为 $m ^ {3/2} t ^ {3/2}/\sqrt {\ epsilon} $，则可将其设为小于 $ \epsilon $ 的错误。

更高顺序的公式（特别是 ($ 2k $) $k>$0 的第一顺序）可递归构造： $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t) ] ^ 2 U_ {2k-2} ( [1-4s_k] t) [U_ {2k-2} (s_k) \~ ] ^ 2 = e ^ {-iHt} + O ( # B11 m t) ^ {2k + 1}/r ^ {2k} ) ，$ $，其中 $s _k = (4-4 ^ {1} (^ {-1} $。

最简单的步骤如下第四个 ($k = $2) 公式，最初由 Suzuki 引入： $ $ U_4 (t) = [U_2 (s_2 \~ t) ] ^ 2 U_2 ( [1-4s_2] t) [U_2 (s_2 \~ t) ] ^ 2 = e ^ {-iHt} + O () ^ 5t ^ 5/r ^ 4 $s，$ $，其中 (_2 = ) ^ {-1} $。
通常，可以按类似方式构造任意高阶公式;然而，使用更复杂的集成商时所产生的成本通常会超出大多数实际问题的第四个订单的权益。

为了使以上策略正常工作，我们需要使用一种方法来模拟 $e ^ {iH_j t} $ 的各种类。
最简单的 Hamiltonians 系列是最有用的，这里我们可以使用 Pauli 运算符。
可以轻松模拟 Pauli 操作员，因为使用 Clifford 操作可以对其进行 diagonalized， (这是量子计算) 的标准入口。
此外，一旦 diagonalized，就可以通过计算其作用的 qubits 的奇偶校验来找到其本征值。

例如，$ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H) ，$ $，其中 $ $ e ^ {-i Z \otimes Z} = \begin{bmatrix} e ^ {-} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {\end{bmatrix}.}
$ $ 这里，$e ^ {-iHt} \ket {00} = e ^ {it} \ket {00} $ and $e ^ {-iHt} \ket {01} = e ^ {-} \ket {01} $，这种情况可以直接查看，因为 $0 $ 的奇偶校验为 $0 $，而位字符串 $1 $ 的奇偶校验为 $1 $。

指数 of Pauli 运算符可在中 Q# 使用操作直接实现 <xref:Microsoft.Quantum.Intrinsic.Exp> ：
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

对于 Fermionic Hamiltonians， [约旦– Wigner 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner) 方便地将 Hamiltonian 映射到 Pauli 运算符之和。
这意味着可以轻松地将上述方法用于模拟化学。
下面只是一个简单的示例，说明如何在 Pauli 中运行这样的模拟，而不是手动遍历 Jordan-Wigner 表示形式中的所有字词。
我们的起点是 Fermionic Hamiltonian 的 [约旦– Wigner 编码](xref:microsoft.quantum.chemistry.concepts.jordanwigner) ，用代码表示为类的实例 `JordanWignerEncoding` 。

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

模拟算法可使用的此格式的约旦– Wigner 表示形式 Q# 是用户定义的类型 `JordanWignerEncodingData` 。
在中 Q# ，此格式会传递到便利性函数，该函数将 `TrotterStepOracle` 使用 Trotter （Suzuki 集成器）除运行所需的其他参数外，返回逼近时间演化的运算符。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要的是，此实现应用了一些优化，其中介绍了如何 [使用量程计算机模拟电子结构 Hamiltonians](https://arxiv.org/abs/1001.3855) ，并 [改进了用于量程化学的量程算法](https://arxiv.org/abs/1403.1539) ，以最大程度地减少所需的 qubit 旋转次数，并减少了模拟错误。

## <a name="qubitization"></a>Qubitization

Qubitization 是一种模拟的替代方法，该方法使用量程行走的想法来模拟量子 dynamics。
尽管 qubitization 需要比 Trotter 公式更多的 qubits，但该方法承诺在发展时间和容错范围内实现最佳缩放。
由于这些原因，它成为了一般模拟 Hamiltonian dynamics 和解决电子结构问题的一种更喜欢方法。

从较高层次来看，qubitization 通过以下步骤完成此操作。
首先，让 $H = \ sum_j h_j 单一和 Hermitian 的 H_j $ $H _j $ 和 $h _j \ge $0。
通过执行一对反射，qubitization 实现等效于 $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1) }，$ $ 其中 $ | h | _1 = \ sum_j | h_j | $ 的运算符。
下一步涉及到将行走操作员的本征值转换为 $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1) } $，其中 $E _k $ 是 $H $ 到 $e ^ {-iE_k t} $ 的本征值。
这可以通过使用各种量程值转换方法（包括 [量程信号处理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)）来实现。

或者，如果只需要静态数量 (例如 Hamiltonian 的地面状态能量) ，则它后缀将 [阶段估算](xref:microsoft.quantum.libraries.characterization) 直接应用到 $W $，以通过采用结果的余弦来估算结果中的地面状态。
这一点很重要，因为它允许 spectral 转换执行经典，而不是使用量子单数值转换方法。

在更详细的级别上，qubitization 的实现需要两个为 Hamiltonian 提供接口的子例程。
与 Trotter – Suzuki 方法不同的是，这些子例程不是经典的，它们的实现需要使用对数比基于 Trotter 的模拟更多的 qubits。

Qubitization 使用的第一个量程子例程称为 $ \operatorname{Select} $，并且承诺生成 \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}，\end{equation}，其中每个 $H _j $ 被认为是 Hermitian 和单一。
虽然这看起来很有限制，但请记住，Pauli 运算符是 Hermitian 的，因此，类似于量子化学模拟的应用程序自然会落到此框架中。
$ \Operatorname{Select} $ 操作（可能令人吃惊）实际上是一个反射操作。
由于每个 $H _j $ 是单一和 \Ket{\psi}，因此具有 Hermitian $ 本征值 $1，因此可从 $ \operatorname{Select} ^ 2 \ 票证 {j} \ket{\psi} = \ket{j} \pm $ 这一事实中了解这一点。

第二个子例程称为 $ \operatorname{Prepare} $。
尽管选择操作提供了一种方法来一致访问每个 Hamiltonian 条款 $H _j $ "准备" 子例程提供了一个方法，用于访问系数 $h _j $、\begin{equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}。
\end{equation} 然后，通过使用多重控制的阶段入口，可以看到 $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{cases} \- \ket{x} & \text{if} x = 0 \\\
        \ket{x} & \text{otherwise} \end{cases}。
$$

$ \Operatorname{Prepare} $ 操作不直接在 qubitization 中使用，而是用于实现 $ \operatorname{Prepare} $ 创建 $ $ \begin{align} R &amp; = 1-2 \ o {Prepare} \ket \bra \operatorname{Prepare} {0} {0} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} 的状态反射。
\end{align} $ $

可以使用 $ \operatorname{Select} $ 和 $R $ 操作数作为 $ $ W = \operatorname{Select} R，$ $ 来表示演练运算符 $W $，该运算符再次可用于实现等效)  (等于 $e ^ {\pm i \cos ^ {-1} (H/| H | _1) } $ 的运算符。

可以在中轻松设置这些子例程 Q# 。
例如，请考虑简单的 qubit 横向 Ising Hamiltonian，其中 $H = X_1 + X_2 + Z_1 Z_2 $。
在这种情况下， Q# 将通过调用实现 $ \operatorname{Select} $ 操作的代码 <xref:Microsoft.Quantum.Canon.MultiplexOperations> ，而 $ \operatorname{Prepare} $ 操作可使用来实现 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState> 。
例如，可以找到模拟 Hubbard 模型的[ Q# 示例。](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard)

手动为任意化学问题指定这些步骤需要花费很多精力，这可避免使用化学库。
与上面的 Trotter – Suzuki 模拟算法类似， `JordanWignerEncodingData` `QubitizationOracle` 除了运行所需的其他参数外，还将传递给返回行走运算符的便利性函数。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要的是，实现 <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> 适用于指定为 Pauli 字符串的线性组合的任意 Hamiltonians。
使用对化学模拟优化的版本进行调用 <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle> 。
此版本经过优化，可将使用 [编码电子 Spectra 时所讨论的技术与线性 t 复杂度进行编码](https://arxiv.org/abs/1805.03662)，从而最大程度地减少 T 入口数。
