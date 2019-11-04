---
title: 相关 wavefunctions |Microsoft Docs
description: 量程 Dynamics 概念文档
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 0b14f373d31c5b63e313e07810daf62d9195b1d3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184026"
---
# <a name="correlated-wavefunctions"></a>相关 wavefunctions

对于很多系统，尤其是接近平衡的几何， [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock)理论通过单行列式引用状态提供分子属性的定性说明。 但是，为了实现定量准确性，还必须考虑相关影响。 

在这种情况下，必须在动态和非动态相关性之间进行 dinstinguish。
Dynamical 相关导致电子的趋势，例如 interelectronic 斥力。 通过在引用状态中考虑 excitations 电子，可以建模这种影响。 如果 wavefunction 由两个或更多配置按第零个的顺序进行，甚至只是为了实现系统的定性说明，则会出现非动态关联。
这就是 superposition 的 qps，而 multireference wavefunction 的示例。

化学库提供了一种方法，用于将 multireference 问题的第零个 order wavefunction 指定为 qps 的 superposition。 当只有几个组件足以指定 superposition 时，此方法（我们称为稀疏 multireference wavefunctions）有效。 该库还提供了一种方法，用于通过通用的单一行列式群集 ansatz 在单个行列式引用之上包含动态关联。 此外，它还构造在量程计算机上生成这些状态的量程电路。 这些状态可能在[Broombridge 架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中指定，并且我们还提供了通过化学库手动指定这些状态的功能。

## <a name="sparse-multi-reference-wavefunction"></a>稀疏多引用 wavefunction
多引用状态 $ \ket{\psi_{\rm {MCSCF}}} $ 可以显式指定为 $N $-electron Slater determininants 的线性组合。
\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1，i_2，\cdots，i_N} a ^ \dagger_{i_1}a ^ \dagger_{i_2}\cdots a ^ \dagger_{i_N}\ket{0}。
例如，\end{align} 可以在化学库中指定 "状态 $ \propto" （0.1 a ^ \dagger_1a ^ \dagger_2a ^ \dagger_6-0.2 a ^ \dagger_2a ^ \dagger_1a ^ \dagger_5） \ket{0}$，如下所示。
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
当只需指定一些组件时，superposition 组件的显式表示形式有效。 如果需要多个组件来准确捕获所需状态，则应避免使用这种表示形式。 导致这种情况的原因是，量程线路的入口成本在量子计算机上准备此状态，这种情况下，最多可使用 superposition 组件进行线性缩放，最多几率 superposition amplitudes。

## <a name="unitary-coupled-cluster-wavefunction"></a>单一耦合群集 wavefunction
还可以使用 chemistery 库指定单一耦合群集 wavefunction $ \ket{\psi_{\rm {UCC}} $。 在这种情况下，我们有一个行列式的引用状态，例如 $ \ket{\psi_{\rm{SCF}}} $。 然后通过充当引用状态的单一运算符指定 implicity 的单一耦合群集 wavefunction 的组件。
此单一运算符通常编写为 $e ^ {T-T ^ \dagger} $，其中 $T-T ^ \dagger $ 是反 Hermitian 群集运算符。 因此 \begin{align} \ket{\psi_{\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\psi_{\rm{SCF}}}。
\end{align}

通常，将群集操作员 $T = T_1 + T_2 + \cdots $ 拆分为多个部分，其中每个部件 $T _j $ 包含 $j $ 正文术语。 在一般化耦合群集理论中，一种正文分类运算符（单精度值）的形式为 \begin{align} T_1 = \sum_{pq}t ^ {p} _ {q} a ^ \dagger_p a_q，\end{align}

和两正文分类运算符（双精度型）的形式为 \begin{align} T_2 = \sum_{pqrs}t ^ {pq} _ {rs} a ^ \dagger_p a ^ \dagger_q a_r a_s。
\end{align}

高阶术语（三元组、可等）是可能的，但不受化学库支持。

例如，让 $ \ket{\psi_{\rm{SCF}}} = a ^ \dagger_1 a ^ \dagger_2\ket{0}$，并让 $T = 0.123 a ^ \dagger_0 a_1 + 0.456 a ^ \dagger_0a ^ \dagger_3 a_1 a_2-0.789 a ^ \dagger_3a ^ \dagger_2 a_1 a_0 $。 然后，此状态在化学库中实例化，如下所示。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

可以通过指定 `SpinOrbital` 索引而不是整数索引来使旋转 convervation 是显式的。 例如，let $ \ket{\psi_{\rm{SCF}}} = a ^ \dagger_{1，\uparrow} a ^ \dagger_{2，\downarrow}\ket{0}$，并让 $T = 0.123 a ^ \dagger_{0，\uparrow} a_ {1，\uparrow} + 0.456 a ^ \dagger_{0，\uparrow} a ^ \dagger_{3，\downarrow} a_ {1，\uparrow} a_ {2，\向下键}-0.789 a ^ \dagger_{3，\uparrow} a ^ \dagger_{2，\uparrow} a_ {1，\uparrow} a_ {0，\uparrow} $ convserving。 然后，此状态在化学库中实例化，如下所示。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

我们还提供了一个方便的函数，用于枚举 annihilate 仅占用了 orbitals 和激发的所有自旋
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```