---
title: 第二量化
description: 了解第二种量化方法，用于在量程编程中对电子结构建模。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: ba77c499d6830b1f78bba39e20b15c4ebe9433fc
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869454"
---
# <a name="second-quantization"></a>第二量化

第二个量化通过不同的镜头查看电子结构的问题。
除了将每个 $N _e $ 电子分配到特定状态 (或 orbital) 外，第二个量化还会跟踪每个 orbital，并存储每个，并同时自动确保相应波形函数的对称属性。
这一点很重要，因为它允许指定量子化学模型，而无需担心 symmetrizing 输入状态 (与 fermions) 所必需的一样，另外，因为第二个量化允许使用小型量子计算机模拟此类模型。

作为第二个量化运算的示例，假设 $ \ psi_0 \cdots \ psi_ {N-1} $ 是一组 orthonormal 的空间 orbitals。
选择这些 orbitals 以尽可能准确地表示所考虑的有限基数内的系统。
此类 orbitals 的一个常见示例是原子 orbitals，它构成 hydrogen atom 的 eigenbasis。
由于电子具有两个自旋状态，因此可将两个电子 crammed 到每个此类空间 orbital 中。
也就是说，有效的基本状态为以下形式： $ \ psi_ {0，\uparrow}，\ldots，\ psi_ {N-1，\uparrow}，\ psi_ {0，\downarrow}，\ldots，\ psi_ {N-1，\downarrow} $，其中 $ \uparrow $ 和 $ \downarrow $ 是指定旋转度的两个 eigenstates 的标签。
此组合索引 $ (j，\sigma) $ for $ \sigma \in \{ \uparrow，\downarrow \} $ 称为旋转 orbital，因为它同时存储空间以及旋转的自由度。
在化学库中，orbitals 存储在 `SpinOrbital` 数据结构中，并按如下所示创建。

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

这意味着我们可以正式考虑将波形函数的旋转空间部分和空间部分的基础作为 $ \ psi_ {0} \cdots \ psi_ {2n-1} $，其中每个索引现在是 $ (j \sigma) $ 的枚举。
一个可能的枚举是 $g (j，\sigma) = j + N\sigma "$。
另一个可能的枚举是 $h (j，\sigma) = 2 * j + \sigma $。
量程化学库可以使用这些约定，因此，这种编码中的 orbitals 可以实例化，如下所示。

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

对于 fermionic 系统，Pauli 排除原则阻止在任何自旋 orbital 同时出现多个 electron。
这意味着我们可以将 $ \ psi_1 $ 的两个合法状态编写为 \begin{equation} \ psi_1 \rightarrow \begin{cases} \ket {0} _1 & \text{if $ \ psi_1 $，}\\\
\ket {1} _1 & \text{if $ \ psi_1 $ 已被占用。} \end{cases} \end{equation} 这种编码非常适合于量子计算机，因为这意味着我们可以将电子职业存储为单个量子位。

$ 2N $ 自旋 orbitals 的职业状态同样可以存储在 $ 2N $ qubits 中。
例如，如果 $N = $2，则状态 $ $ \ket {0} \ket {1} \ket {1} \ket {0} ，$ $

对应于自旋 orbitals $1 $ 和 $2 $，其余数为空。
同样，状态 $ $ \ket {0} \equiv \ket {0} _ {0} {0} \cdots \ket_{N-1}，$ $

没有电子，称为 "真空度"。

第二个量化的一个漂亮副作用是，我们不再需要显式跟踪量程状态的反对称性。
这是因为，正如我们所看到的，该状态的反对称改为通过创建和销毁旋转 orbital 的电子职业的运算符的反通信规则来表示自身。

## <a name="fermionic-operators"></a>Fermionic 运算符

作用于第二量化基础向量的两个基本运算符称为创建和 annihilation 运算符。
这些运算符在特定位置插入或销毁电子。
它们分别表示 $a ^ \ dagger_j $ 和 $a _j $。

例如，\begin{align} 为 ^ \ dagger_1 \ket {0} _1 = \ket {1} _1，\quad a ^ \ dagger_1 \ket {1} _1 = 0，\quad a_1 \ket {0} _1 = 0，\quad a_1 \ket {1} _1 = \ket {0} _1。
\end{align} 请注意，此处 $a ^ \ dagger_1 \ket {1} _1 = 0 $，$a _1 \ket {0} _1 $ yield 0 矢量 not $ \ket {0} _1 $。
因此，此类运算符既不是 Hermitian 也不是单一运算符。
我们使用类型来表示常规创建和 annihilation 运算符 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> 。
例如，单个创建运算符按如下方式表示。

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

另外，还可以使用此类运算符来表达 $ $ \ket {0} \ket {1} \ket {1} \ket {0} = ^ \ dagger_1 ^ \ dagger_2 \ket {0} ^ {\otimes 4}。
$ $ 此运算符序列将使用 c # 代码在 Hamiltonian 模拟库中构造，此代码类似于上面所示的单一旋转 orbital 大小写：
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

对于 $k $ Fermions 的系统，在第二个量化中，$a ^ \ dagger_i $ 的创建操作员的操作由 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、0_i、\ldots、n_k} = (-1) ^ {S_i} \ket{n_1、n_2、\ldots 1_i、\ldots、n_k}、$ $ 和 $ $ a ^ \ dagger_i \ket{n_1，n_2，\ldots，1_i，\ldots，n_k} = 0，$ $，其中 $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ 度量处于单个粒子状态且索引 $j < i $ 的 Fermions 总数。

第三个运算符也经常用在第二个量化表示形式中。
此运算符被称为 number 运算符，由 \begin{equation} n_i = a ^ \ dagger_i a_i 定义。
\end{equation} 此运算符可计算给定旋转 orbital 的职业，这就是说 \begin{align} n_i \ket {0} _i &= 0 \ nonumber\\\
n_i \ket {1} _i &= \ket {1} _i。
\end{align} 类似于上述 `FermionTerm` 示例，此数字运算符按如下方式构造。
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

使用 fermionic 系统中的创建或 annihilation 运算符时，将出现个很微妙。
我们要求在 "标签交换" 下，任何有效的量程状态都为抗对称状态。
这意味着 $ $ a ^ \ dagger_2 ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket {0} 。
$ $ 此类运算符被称为 "反双回"，一般适用于任何 $i，j $ 我们已 \begin{align} ^ \ dagger_i ^ \ dagger_j =- (1-\ delta_ {i，j} ) ^ \ dagger_j ^ \ dagger_i，\quad ^ \ dagger_i a_j = \ delta_ {i，j}-a_j ^ \ dagger_i。
\end{align} 因此，以下两个 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> 实例被视为 inequivalent
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

每个创建运算符的反上下班的要求是，使用第二个量化表示形式会这样就不 Fermions 反对称所面临的挑战。
而是在创建操作员的定义中重新出现。 

使用反通信规则时，某些 `LadderSequence` 实例实际上对应于相同的 fermionic 运算符序列，有时最多会有一个负号。
例如，请考虑 Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $。
这激发我们为每个定义一个规范排序 `FermionTerm` 。
Any `FermionTerm` 将按如下方式自动纳入规范顺序。
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a>量化 Fermionic Hamiltonian

可能 unsurprising，可以通过创建和 annihilation 运算符来编写[适用于电子系统的量程模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中的 Hamiltonian。
具体而言，如果 $ \psi \_ j $ 是形成基础的旋转 orbitals，

\begin{equation} \hat{H} = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ Ra \_ s + H \_ {\textrm nuc}，\label{eq： totalHam} \end{equation}，其中 $h \_ {\textrm nuc} $ (是在) 

\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3 \_ 1，\end{align}

其中 $V (x) $ 是 "平均" 字段的潜力，

\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left ( \frac {1} {| x_1 \_ x \_ 2 x_2 \right) \_ x \_ 1 (\psi ^ 3 x \_ \psi {d} ^ 3 \_ ： \mathrm{d}

术语 $h \_ {pq} $ 称为 electron 积分，因为所有这类条款仅涉及单个电子，同样 $h \_ {pqrs} $ 是两个 electron 整型。
它们被称为整型，因为计算这些系数的值需要整数值。
一 electron 的术语说明了单个电子的 kinetic 能量，并说明了与 nuclei 的电子字段的交互。
另一方面，electron 的整型描述电子之间的交互。

对于这些术语的含义，直觉可从包含每个术语的创建和 annihilation 运算符搜集。
例如，$h _ {pq} a ^ \ dagger_p a_q $ 描述从自旋 orbital $q $ 到自旋 orbital $p $ 的 electron 跳跃。
同样，术语 $h _ {pqrs} a ^ \ dagger_p ^ \ dagger_q a_r a_s $ (对于 distinct $p，q，r，s $) 介绍了自旋 orbitals $r $ 和 $s $ 分散之间的两个电子，并最终在自旋 orbitals $p $ 和 $q $。
如果 $r = q $ and $p = s $，则 $h _ {prrp} a ^ \ dagger_p ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ 为与这两个电子关联的能源损失进行了关联，但不描述 dynamical 过程。

我们可能会使用类来表示此类 Hamiltonians `FermionHamiltonian` ，该类实质上是包含所有所需实例的列表 `FermionTerm` 。
由于 Hamiltonians 是按定义 Hermitian 的，因此，我们使用更专业化的类型为术语编制索引，该类型在 `HermitianFermionTerm` 检查字词是否等效时也使用 Hermitian 对称。

让我们构造一些直观的示例。
请考虑 Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $。
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
我们可以使用 Hamiltonian 运算符是 Hermitian 运算符这一事实来简化此构造。
当使用将术语添加到 Hamiltonian 时 `Add` ，所有非 Hermitian 术语（如） `fermionTerm0` 都假设与 Hermitian 共轭成对使用。
因此，以下代码片段还表示相同的 Hamiltonian：
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

使用反通信规则时， `FermionTerm` Hamiltonian 中的某些实例实际上对应于相同的 fermionic 运算符序列，有时最大为减号。
例如，请考虑 Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $，这是上面所构造的条款之和。
用户可能并不总是清楚地说它们是等效的，因此可能会将它们分别添加到 Hamiltonian 中。
或者，可能有兴趣修改 Hamiltonian 中已有的术语。
在这些情况下，我们可能会按如下所示组合相同的术语。
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
通过组合等效术语的系数，减少了 Hamiltonian 中的总字词数。
稍后，这减少了模拟 Hamiltonian 所需的量程入口数。

### <a name="internal-representation"></a>内部表示形式

具有一到两正文交互的 fermionic Hamiltonian 以第量化表示法表示为

$ $ \begin{align} H = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s}。
\end{align} $ $

在此表示法中，最多 $N ^ 2 + N ^ 4 $ 系数。
但是，可能会收集其中许多系数，因为它们对应于同一个运算符。
例如，在 $p、q、r、s $ 是不同的索引，我们可以使用反通信规则显示： $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {s} a \_ {r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {s} a \_ {r}。
$$

此外，由于 $H $ 是 Hermitian 的，因此每个非 Hermitian fermionic 运算符（如 $h \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $）都具有一个 Hermitian $H 共轭。 为了唯一索引按这些 symmetries 的术语组，我们在索引 $ (i \_ 1，\cdots，i \_ n，j \_ 1，\cdots，j \_ m) $，定义 $n + m $ fermionic 运算符 $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j m} $as 的标准排序， \_ 如下所示：
-   所有创建操作员 $a ^ \dagger \_ {i \_ \cdot} $ 位于所有 annihilation 运算符之前 $a \_ {j \_ \cdot} $。
-   所有创建运算符索引按升序排序，即 $i \_ 1< i \_ 2< \cdots < i \_ n $。
-   所有 annihilation 运算符索引按降序排序，即 $j \_ 1> j \_ 2 \cdots > j \_ m $。
-   最左侧的索引小于或等于最右侧的索引，该索引 $i \_ 1 \ le j \_ m $。

让我们将这组规范有序索引标识为 $ $ \begin{align} (i \_ 1、\cdots、i \_ n、j \_ 1、\cdots、j \_ m) \in S \_ {n，m}。
\end{align} $ $

使用此规范排序，fermionic Hamiltonian 可表示为 $ $ \begin{align} H = \sum \_ { (p，q) \In S \_ {1,1} } H ' \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ { (p，q，r，S) \in s \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {S} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} ，\end{align} $ $，经过适当调整的 electron 整型 $h " \_ {pq} $ 和 $h" \_ {pqrs} $。

