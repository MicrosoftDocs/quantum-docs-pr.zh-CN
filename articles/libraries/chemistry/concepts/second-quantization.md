---
title: 第二量化
description: 了解第二种量化方法，用于在量程编程中对电子结构建模。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: e17c97767b05395af46a82c4035337406c7e3218
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907335"
---
# <a name="second-quantization"></a><span data-ttu-id="3c8a2-103">第二量化</span><span class="sxs-lookup"><span data-stu-id="3c8a2-103">Second Quantization</span></span>

<span data-ttu-id="3c8a2-104">第二个量化通过不同的镜头查看电子结构的问题。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="3c8a2-105">除了将每个 $N _e $ 电子分配到特定状态（或 orbital），第二个量化都将跟踪每个 orbital 并存储每个中是否存在 electron，同时自动确保对应的波形函数。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="3c8a2-106">这一点很重要，因为它允许指定量子化学模型，而无需担心反 symmetrizing 输入状态（对于 fermions 是必需的），也是因为第二个量化允许使用小型量子模拟此类模型计算机.</span><span class="sxs-lookup"><span data-stu-id="3c8a2-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="3c8a2-107">作为第二个量化运算的示例，假设 $ \ psi_0 \cdots \ psi_ {N-1} $ 是一组 orthonormal 的空间 orbitals。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="3c8a2-108">选择这些 orbitals 以尽可能准确地表示所考虑的有限基数内的系统。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="3c8a2-109">此类 orbitals 的一个常见示例是原子 orbitals，它构成 hydrogen atom 的 eigenbasis。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="3c8a2-110">由于电子具有两个自旋状态，因此可将两个电子 crammed 到每个此类空间 orbital 中。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="3c8a2-111">也就是说，有效的基本状态为以下形式： $ \ psi_ {0，\uparrow}，\ldots，\ psi_ {N-1，\uparrow}，\ psi_ {0，\downarrow}，\ldots，\ psi_ {N-1，\downarrow} $，其中 $ \uparrow $ 和 $ \downarrow $ 是指定任意.</span><span class="sxs-lookup"><span data-stu-id="3c8a2-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="3c8a2-112">$ （J，\sigma） $ 的此组合索引为 $ \sigma \in \{\uparrow，\downarrow\}$ 称为旋转 orbital，因为它同时存储空间以及旋转的自由度。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="3c8a2-113">在化学库中，orbitals 存储在 `SpinOrbital` 数据结构中，并按如下所示创建。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

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

<span data-ttu-id="3c8a2-114">这意味着我们可以正式考虑将波形函数的旋转空间部分和空间部分的基础作为 $ \ psi_{0} \cdots \ psi_ {2N-1} $，其中每个索引现在是 $ （j，\sigma） $ 的枚举。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="3c8a2-115">一个可能的枚举是 $g （j，\sigma） = j + N\sigma "$。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="3c8a2-116">另一个可能的枚举是 $h （j，\sigma） = 2 \* j + \sigma $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="3c8a2-117">量程化学库可以使用这些约定，因此，这种编码中的 orbitals 可以实例化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

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

<span data-ttu-id="3c8a2-118">对于 fermionic 系统，Pauli 排除原则阻止在任何自旋 orbital 同时出现多个 electron。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="3c8a2-119">这意味着我们可以将 $ \ psi_1 $ 的两个合法状态编写为 \begin{equation} \ psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $ \ psi_1 $，} </span><span class="sxs-lookup"><span data-stu-id="3c8a2-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="3c8a2-120">\ket{1}_1 & \text{if $ \ psi_1 $ 已被占用。}</span><span class="sxs-lookup"><span data-stu-id="3c8a2-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="3c8a2-121">\end{cases} \end{equation} 这种编码非常适合于量子计算机，因为这意味着我们可以将电子职业存储为单个量子位。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="3c8a2-122">$ 2N $ 自旋 orbitals 的职业状态同样可以存储在 $ 2N $ qubits 中。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="3c8a2-123">例如，如果 $N = $2，则状态 $ $ \ket{0} \ket{1} \ket{1} \ket{0}，$ $</span><span class="sxs-lookup"><span data-stu-id="3c8a2-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="3c8a2-124">对应于自旋 orbitals $1 $ 和 $2 $，其余数为空。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="3c8a2-125">同样，状态 $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}，$ $</span><span class="sxs-lookup"><span data-stu-id="3c8a2-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="3c8a2-126">没有电子，称为 "真空度"。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="3c8a2-127">第二个量化的一个漂亮副作用是，我们不再需要显式跟踪量程状态的反对称性。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="3c8a2-128">这是因为，正如我们所看到的，该状态的反对称改为通过创建和销毁旋转 orbital 的电子职业的运算符的反通信规则来表示自身。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="3c8a2-129">Fermionic 运算符</span><span class="sxs-lookup"><span data-stu-id="3c8a2-129">Fermionic operators</span></span>

<span data-ttu-id="3c8a2-130">作用于第二量化基础向量的两个基本运算符称为创建和 annihilation 运算符。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="3c8a2-131">这些运算符在特定位置插入或销毁电子。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="3c8a2-132">它们分别表示 $a ^ \ dagger_j $ 和 $a _j $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="3c8a2-133">例如，\begin{align} dagger_1 \ket{0}_1 = \ket{1}_1，\quad a ^ \ dagger_1 \ket{1}_1 = 0，\quad a_1 \ket{0}_1 = 0，\quad a_1 \ket{1}_1 = \ket{0}_1。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="3c8a2-134">\end{align} 请注意，此处 $a ^ \ dagger_1 \ket{1}_1 = 0 $ 和 $a _1 \ket{0}_1 $ yield 0 矢量 not $ \ket{0}_1 $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="3c8a2-135">因此，此类运算符既不是 Hermitian 也不是单一运算符。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="3c8a2-136">我们使用 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> 类型来表示常规创建和 annihilation 运算符。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="3c8a2-137">例如，单个创建运算符按如下方式表示。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-137">For instance, a single creation operator is represented as follow.</span></span>

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

<span data-ttu-id="3c8a2-138">另外，还可以使用此类运算符来表达 $ $ \ket{0} \ket{1} \ket{1} \ket{0} = ^ \ dagger_1 ^ \ dagger_2 \ket{0}^ {\otimes 4}。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="3c8a2-139">$ $ 此运算符序列将使用C#类似于上面所示的单旋转 orbital 大小写的代码在 Hamiltonian 模拟库中构造。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
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

<span data-ttu-id="3c8a2-140">对于 $k $ Fermions 的系统，在第二个量化中，$a ^ \ dagger_i $ 的创建操作员的操作由 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、0_i、\ldots、n_k} = （-1） ^ {S_i} \ket{n_1、n_2、\ldots 1_i、\ldots、n_k}、$ $ 和 $ $ a ^ \ dagger_i \ket{n_1，n_2，\ldots，1_i，\ldots，n_k} = 0，$ $，其中 $S _i = \ sum_ {j < i} a ^ \ dagger_j a_j $ 度量处于单个粒子状态且索引 $j < i $ 的 Fermions 总数。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="3c8a2-141">第三个运算符也经常用在第二个量化表示形式中。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="3c8a2-142">此运算符被称为 number 运算符，由 \begin{equation} n_i = a ^ \ dagger_i a_i 定义。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="3c8a2-143">\end{equation} 此运算符可计算给定旋转 orbital 的职业，这就是说 \begin{align} n_i \ket{0}_i & = 0 \ nonumber</span><span class="sxs-lookup"><span data-stu-id="3c8a2-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="3c8a2-144">n_i \ket{1}_i & = \ket{1}_i。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="3c8a2-145">\end{align} 类似于上述 `FermionTerm` 示例，此数字运算符按如下方式构造。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
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

<span data-ttu-id="3c8a2-146">使用 fermionic 系统中的创建或 annihilation 运算符时，将出现个很微妙。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="3c8a2-147">我们要求在 "标签交换" 下，任何有效的量程状态都为抗对称状态。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="3c8a2-148">这意味着 $ $ a ^ \ dagger_2 ^ \ dagger_1 \ket{0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket{0}。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="3c8a2-149">$ $ 此类运算符称为 "反双回"，一般适用于任何 $i，j $ 我们已 \begin{align} ^ \ dagger_i ^ \ dagger_j =-（1-\ delta_ {i，j}） ^ \ dagger_j ^ \ dagger_i，\quad，^ \ dagger_i a_j = \ delta_ {i，j}-a_j ^ \ dagger_i。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="3c8a2-150">\end{align} 因此，以下两个 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> 实例被视为 inequivalent</span><span class="sxs-lookup"><span data-stu-id="3c8a2-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
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

<span data-ttu-id="3c8a2-151">每个创建运算符的反上下班的要求是，使用第二个量化表示形式会这样就不 Fermions 反对称所面临的挑战。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="3c8a2-152">而是在创建操作员的定义中重新出现。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="3c8a2-153">使用反通信规则时，某些 `LadderSequence` 实例实际上对应于相同的 fermionic 运算符序列，有时最大为减号。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="3c8a2-154">例如，请考虑 Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="3c8a2-155">这激发我们为每个 `FermionTerm`定义规范排序。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="3c8a2-156">任何 `FermionTerm` 都将按如下方式自动纳入规范顺序。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
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

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="3c8a2-157">量化 Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="3c8a2-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="3c8a2-158">可能 unsurprising，可以通过创建和 annihilation 运算符来编写[适用于电子系统的量程模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="3c8a2-159">具体而言，如果 $ \psi\_j $ 是形成基础的旋转 orbitals，则</span><span class="sxs-lookup"><span data-stu-id="3c8a2-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="3c8a2-160">\begin{equation} \hat{H} = \sum\_{pq} H\_{pq} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_p a ^ \dagger\_q a\_ra\_s + H\_{\textrm nuc}，\label{eq： totalHam} \end{equation}，其中 $h\_{\textrm nuc} $ 是核能量（这是一种在近似值下的常量），</span><span class="sxs-lookup"><span data-stu-id="3c8a2-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="3c8a2-161">\begin{align} h\_{pq} & = \int\_{-\infty} ^ \infty \psi ^\*\_p （x\_1） \left （-\frac{\nabla ^ 2}{2} + V （x\_1） \right） \psi\_q （x\_1） \mathrm{d} ^ 3\_1，\end{align}</span><span class="sxs-lookup"><span data-stu-id="3c8a2-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="3c8a2-162">其中 $V （x） $ 是可能的平均字段，并且</span><span class="sxs-lookup"><span data-stu-id="3c8a2-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="3c8a2-163">\begin{align} h\_{pqrs} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*（x\_1） \psi\_q ^\*（x\_2） \left （\frac{1}{| x_1-x_2 |} \right） \psi\_r （x\_2） \psi\_s （x\_1） \mathrm{d} ^ 3\_1 \ mathrm {d} ^ 3\_2。 \ 标签 {eq：积分} \end{align}</span><span class="sxs-lookup"><span data-stu-id="3c8a2-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="3c8a2-164">\_{pq} $ $h 术语称为 electron 整型，因为所有这类条款仅涉及单个电子，同样 $h\_{pqrs} $ 是两个 electron 整型。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="3c8a2-165">它们被称为整型，因为计算这些系数的值需要整数值。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="3c8a2-166">一 electron 的术语说明了单个电子的 kinetic 能量，并说明了与 nuclei 的电子字段的交互。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="3c8a2-167">另一方面，electron 的整型描述电子之间的交互。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="3c8a2-168">对于这些术语的含义，直觉可从包含每个术语的创建和 annihilation 运算符搜集。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="3c8a2-169">例如，$h _ {pq} a ^ \ dagger_p a_q $ 描述从自旋 orbital $q $ 到自旋 orbital $p $ 的 electron 跳跃。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="3c8a2-170">同样，术语 $h _ {pqrs} a ^ \ dagger_p ^ \ dagger_q a_r a_s $ （对于 distinct $p，q，r，s $）介绍了自旋 orbitals $r $ 和 $s $ 分散之间的两个电子，并最终在自旋 orbitals $p $ 和 $q $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="3c8a2-171">如果 $r = q $ and $p = s $，则 $h _ {prrp} a ^ \ dagger_p ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ 为与这两个电子关联的能源损失进行了关联，但不描述 dynamical 过程。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="3c8a2-172">我们可能使用 `FermionHamiltonian` 类来表示此类 Hamiltonians，该类实质上是包含所有所需 `FermionTerm` 实例的列表。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="3c8a2-173">由于 Hamiltonians 是按定义 Hermitian 的，因此，我们使用更专业化的类型 `HermitianFermionTerm` 来编制术语的索引，当检查字词是否等效时也使用 Hermitian 对称。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="3c8a2-174">让我们构造一些直观的示例。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="3c8a2-175">请考虑 Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
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
<span data-ttu-id="3c8a2-176">我们可以使用 Hamiltonian 运算符是 Hermitian 运算符这一事实来简化此构造。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="3c8a2-177">使用 `Add`将术语添加到 Hamiltonian 时，所有非 Hermitian 术语（如 `fermionTerm0`）都假设与 Hermitian 共轭成对使用。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="3c8a2-178">因此，以下代码片段还表示相同的 Hamiltonian：</span><span class="sxs-lookup"><span data-stu-id="3c8a2-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="3c8a2-179">使用反通信规则时，Hamiltonian 中的某些 `FermionTerm` 实例实际上对应于相同的 fermionic 运算符序列，有时最大为减号。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="3c8a2-180">例如，请考虑 Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $，这是上面所构造的条款之和。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="3c8a2-181">用户可能并不总是清楚地说它们是等效的，因此可能会将它们分别添加到 Hamiltonian 中。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="3c8a2-182">或者，可能有兴趣修改 Hamiltonian 中已有的术语。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="3c8a2-183">在这些情况下，我们可能会按如下所示组合相同的术语。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-183">In these cases, we may combine equivalent terms as follows.</span></span>
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
<span data-ttu-id="3c8a2-184">通过组合等效术语的系数，减少了 Hamiltonian 中的总字词数。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="3c8a2-185">稍后，这减少了模拟 Hamiltonian 所需的量程入口数。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="3c8a2-186">内部表示形式</span><span class="sxs-lookup"><span data-stu-id="3c8a2-186">Internal Representation</span></span>

<span data-ttu-id="3c8a2-187">具有一到两正文交互的 fermionic Hamiltonian 以第量化表示法表示为</span><span class="sxs-lookup"><span data-stu-id="3c8a2-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="3c8a2-188">$ $ \begin{align} H = \sum\_{pq} H\_{pq} a ^ \dagger\_{p}\_{q} + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s}。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="3c8a2-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3c8a2-189">\end{align} $$</span></span>

<span data-ttu-id="3c8a2-190">在此表示法中，最多 $N ^ 2 + N ^ 4 $ 系数。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="3c8a2-191">但是，可能会收集其中许多系数，因为它们对应于同一个运算符。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="3c8a2-192">例如，在 $p、q、r、s $ 是不同的索引，我们可以使用反通信规则显示： $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{r} a\_{s} =-a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{s}\_{r} = a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{r}\_{s}。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="3c8a2-193">此外，由于 $H $ 是 Hermitian 的，因此每个非 Hermitian fermionic 运算符都假设 $h\_{pqrs} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $，还可以在 $H $ 中找到 Hermitian 共轭。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="3c8a2-194">为了唯一索引按这些 symmetries 的术语组，我们在索引 $ （i\_1、\cdots、i\_n、j\_1、\cdots、j\_m）上定义一个规范排序，其中任何 $n + m $ fermionic 运算符序列 $a ^ \dagger\_{i\_1} \cdots a ^ \dagger\_{i\_n}\_{j\_1} \cdots:\_\_</span><span class="sxs-lookup"><span data-stu-id="3c8a2-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="3c8a2-195">所有创建操作员 $a ^ \dagger\_{i\_\cdot} $ 位于所有 annihilation 运算符之前，$a\_{j\_\cdot} $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="3c8a2-196">所有创建运算符索引将按升序排序，$i\_1 <\_2 < <\_n $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="3c8a2-197">所有 annihilation 运算符索引按降序排序 $j，即\_1 > j\_2 \cdots > j\_m $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="3c8a2-198">最左侧的索引小于或等于最右边的索引，该索引 $i\_1 \ le j\_m $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="3c8a2-199">让我们将这组规范的有序索引标识为 $ $ \begin{align} （i\_1、\cdots、i\_n、j\_1、\_\_\cdots</span><span class="sxs-lookup"><span data-stu-id="3c8a2-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="3c8a2-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3c8a2-200">\end{align} $$</span></span>

<span data-ttu-id="3c8a2-201">使用此规范排序，fermionic Hamiltonian 可表示为 $ $ \begin{align} H = \sum\_{（p，q） \in S\_{1,1}} H "\_{pq} \frac{a ^ \dagger\_{p} a\_{q} + a ^ \dagger\_{q} a\_{p}}{2}+ \sum\_{（p，q、r、S） \in S\_{2,2}} H '\_{pqrs} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} + a ^ \dagger\_{s} a ^ \剑号\_{r} a\_{q} a\_{p}}{2}，\end{align} $ $ 以及适当调整的一个和两个 electron 积分 $h "\_{pq} $ 和 $h '\_{pqrs} $。</span><span class="sxs-lookup"><span data-stu-id="3c8a2-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

