---
title: 相关波函数
description: 使用 Microsoft 量程化学库了解 wavefunctions 中的动态和非动态关联。
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: 420fc8e108852f6548e2147693e089f5ce970aa9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835479"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="21b5d-103">相关波函数</span><span class="sxs-lookup"><span data-stu-id="21b5d-103">Correlated wavefunctions</span></span>

<span data-ttu-id="21b5d-104">对于很多系统，尤其是接近平衡的几何， [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) 理论通过单行列式引用状态提供分子属性的定性说明。</span><span class="sxs-lookup"><span data-stu-id="21b5d-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="21b5d-105">但是，为了实现定量准确性，还必须考虑相关影响。</span><span class="sxs-lookup"><span data-stu-id="21b5d-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="21b5d-106">在这种情况下，必须在动态和非动态相关性之间进行 dinstinguish。</span><span class="sxs-lookup"><span data-stu-id="21b5d-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="21b5d-107">Dynamical 相关导致电子的趋势，例如 interelectronic 斥力。</span><span class="sxs-lookup"><span data-stu-id="21b5d-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="21b5d-108">通过在引用状态中考虑 excitations 电子，可以建模这种影响。</span><span class="sxs-lookup"><span data-stu-id="21b5d-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="21b5d-109">如果 wavefunction 由两个或更多配置按第零个的顺序进行，甚至只是为了实现系统的定性说明，则会出现非动态关联。</span><span class="sxs-lookup"><span data-stu-id="21b5d-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="21b5d-110">这就是 superposition 的 qps，而 multireference wavefunction 的示例。</span><span class="sxs-lookup"><span data-stu-id="21b5d-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="21b5d-111">化学库提供了一种方法，用于将 multireference 问题的第零个 order wavefunction 指定为 qps 的 superposition。</span><span class="sxs-lookup"><span data-stu-id="21b5d-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="21b5d-112">当只有几个组件足以指定 superposition 时，此方法（我们称为稀疏 multireference wavefunctions）有效。</span><span class="sxs-lookup"><span data-stu-id="21b5d-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="21b5d-113">该库还提供了一种方法，用于通过通用的单一行列式群集 ansatz 在单个行列式引用之上包含动态关联。</span><span class="sxs-lookup"><span data-stu-id="21b5d-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="21b5d-114">此外，它还构造在量程计算机上生成这些状态的量程电路。</span><span class="sxs-lookup"><span data-stu-id="21b5d-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="21b5d-115">这些状态可能在 [Broombridge 架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中指定，并且我们还提供了通过化学库手动指定这些状态的功能。</span><span class="sxs-lookup"><span data-stu-id="21b5d-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="21b5d-116">稀疏多引用 wavefunction</span><span class="sxs-lookup"><span data-stu-id="21b5d-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="21b5d-117">多引用状态 $ \ket{\ psi_ {\rm {MCSCF}}} $ 可以显式指定为 $N $-electron Slater determininants 的线性组合。</span><span class="sxs-lookup"><span data-stu-id="21b5d-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="21b5d-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1，i_2，\cdots，i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} 。</span><span class="sxs-lookup"><span data-stu-id="21b5d-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="21b5d-119">\end{align} 例如，state $ \propto (0.1 dagger_1a ^ \ dagger_2a ^ \ dagger_6-0.2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5 \ket {0} $ 可在化学库中指定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21b5d-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
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
<span data-ttu-id="21b5d-120">当只需指定一些组件时，superposition 组件的显式表示形式有效。</span><span class="sxs-lookup"><span data-stu-id="21b5d-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="21b5d-121">如果需要多个组件来准确捕获所需状态，则应避免使用这种表示形式。</span><span class="sxs-lookup"><span data-stu-id="21b5d-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="21b5d-122">导致这种情况的原因是，量程线路的入口成本在量子计算机上准备此状态，这种情况下，最多可使用 superposition 组件进行线性缩放，最多几率 superposition amplitudes。</span><span class="sxs-lookup"><span data-stu-id="21b5d-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="21b5d-123">单一耦合群集 wavefunction</span><span class="sxs-lookup"><span data-stu-id="21b5d-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="21b5d-124">还可以使用 chemistery 库指定单一耦合群集 wavefunction $ \ket{\ psi_ {\rm {UCC}} $。</span><span class="sxs-lookup"><span data-stu-id="21b5d-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="21b5d-125">在这种情况下，我们有一个行列式的引用状态，例如，$ \ket{\ psi_ {\rm{SCF}}} $。</span><span class="sxs-lookup"><span data-stu-id="21b5d-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="21b5d-126">然后通过充当引用状态的单一运算符指定 implicity 的单一耦合群集 wavefunction 的组件。</span><span class="sxs-lookup"><span data-stu-id="21b5d-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="21b5d-127">此单一运算符通常编写为 $e ^ {T-T ^ \dagger} $，其中 $T-T ^ \dagger $ 是反 Hermitian 群集运算符。</span><span class="sxs-lookup"><span data-stu-id="21b5d-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="21b5d-128">因此，\begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T t ^ \dagger}\ket{\ psi_ {\rm{SCF}}}。</span><span class="sxs-lookup"><span data-stu-id="21b5d-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="21b5d-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="21b5d-129">\end{align}</span></span>

<span data-ttu-id="21b5d-130">通常，将群集运算符 $T = T_1 + T_2 + \cdots $ 分为几个部分，其中每个部分 $T _j $ 包含 $j $ 正文术语。</span><span class="sxs-lookup"><span data-stu-id="21b5d-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="21b5d-131">在一般化耦合群集理论中， (单精度值) 的单正文分类操作员的形式为 \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q、\end{align}</span><span class="sxs-lookup"><span data-stu-id="21b5d-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="21b5d-132">和两主体群集运算符 (双精度) 的形式为 \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {rs} a ^ \ dagger_p ^ \ dagger_q a_r a_s。</span><span class="sxs-lookup"><span data-stu-id="21b5d-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="21b5d-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="21b5d-133">\end{align}</span></span>

<span data-ttu-id="21b5d-134">高阶条款 (为三元组、可等 ) ，但化学库当前不支持。</span><span class="sxs-lookup"><span data-stu-id="21b5d-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="21b5d-135">例如，让 $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} $，并让 $T = 0.123 ^ \ dagger_0 a_1 + 0.456 a ^ \ dagger_0a ^ \ 0.789 dagger_3 a_1 a_2 dagger_3a dagger_2 a_1 $。</span><span class="sxs-lookup"><span data-stu-id="21b5d-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="21b5d-136">然后，此状态在化学库中实例化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21b5d-136">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="21b5d-137">可以通过指定 `SpinOrbital` 索引而不是整数索引来使 convervation 变得明确。</span><span class="sxs-lookup"><span data-stu-id="21b5d-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="21b5d-138">例如，让 $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1，\uparrow} ^ \ dagger_ {2，\downarrow}\ket {0} $，并让 $T = 0.123 a ^ \ dagger_ {0，\uparrow} a_ {1，\uparrow} + 0.456 a ^ \ dagger_ {0，\uparrow} a ^ \ dagger_ {3，\downarrow} a_ {1，\uparrow} a_ {2，\downarrow}-0.789 a ^ \ dagger_ {3，\uparrow} a ^ \ dagger_ {2，\uparrow} a_ {1，\uparrow} a_ {0，\uparrow} $ 为自旋 convserving。</span><span class="sxs-lookup"><span data-stu-id="21b5d-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="21b5d-139">然后，此状态在化学库中实例化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21b5d-139">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="21b5d-140">我们还提供了一个方便的函数，用于枚举 annihilate 仅占用了 orbitals 和激发的所有自旋</span><span class="sxs-lookup"><span data-stu-id="21b5d-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
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
