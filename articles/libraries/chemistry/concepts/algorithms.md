---
title: 模拟 Hamiltonian Dynamics |Microsoft Docs
description: 模拟 Hamiltonian Dynamics 概念文档
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 905b03478d453e475fc1e49ea5f88dd0cd2704bc
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184060"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="73ff9-103">模拟 Hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="73ff9-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="73ff9-104">将 Hamiltonian 表示为基本运算符的总和后，就可以使用一系列众所周知的技术将 dynamics 编译为基本的入口操作。</span><span class="sxs-lookup"><span data-stu-id="73ff9-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="73ff9-105">有三种有效的方法，包括 Trotter – Suzuki 公式、unitaries 和 qubitization 的线性组合。</span><span class="sxs-lookup"><span data-stu-id="73ff9-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="73ff9-106">我们将介绍以下三种方法，并为具体的 Q # 示例，了解如何使用 Hamiltonian 模拟库实现这些方法。</span><span class="sxs-lookup"><span data-stu-id="73ff9-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="73ff9-107">Trotter – Suzuki 公式</span><span class="sxs-lookup"><span data-stu-id="73ff9-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="73ff9-108">Trotter – Suzuki 公式背后的理念非常简单：将 Hamiltonian 表达为易于模拟 Hamiltonians，然后以这些更简单的今后的序列来估算总体演变。</span><span class="sxs-lookup"><span data-stu-id="73ff9-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="73ff9-109">具体而言，让 $H = \sum_{j = 1} ^ m H_j $ 为 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="73ff9-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="73ff9-110">然后，$ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \prod_{j = 1} ^ m e ^ {-iH_j t} + O （m ^ 2 t ^ 2），$ $ 这就是，如果 $t \ll $1，则此近似值中的错误将变为可忽略的。</span><span class="sxs-lookup"><span data-stu-id="73ff9-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="73ff9-111">请注意，如果 $e ^ {-i H t} $ 是普通指数，则不会 $O 此近似中的错误（m ^ 2 t ^ 2） $：该值为零。</span><span class="sxs-lookup"><span data-stu-id="73ff9-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="73ff9-112">之所以发生此错误，是因为 $e ^ {-iHt} $ 是运算符指数，因此，使用此公式时出现错误，原因是 $H _j $ 术语不进行上下班（*即*$H _j H_k \ne H_k $）。</span><span class="sxs-lookup"><span data-stu-id="73ff9-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="73ff9-113">如果 $t $ 是大的，则仍可以使用 Trotter – Suzuki 公式来准确模拟动态，方法是将其分解为一系列简短的时间。</span><span class="sxs-lookup"><span data-stu-id="73ff9-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="73ff9-114">让 $r $ 是在时间演进中执行的步骤数。</span><span class="sxs-lookup"><span data-stu-id="73ff9-114">Let $r$ be the number of steps taken in the time evolution.</span></span>
<span data-ttu-id="73ff9-115">接下来，我们将使用 $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \left （\prod_{j = 1} ^ m e ^ {-iH_j t/r} \ right） ^ r + O （m ^ 2 t ^ 2/r），$ $ 这意味着如果 $r $ 缩放为 $m ^ 2 t ^ 2/\ epsilon $，则对于任何 $ \epsilon，最多可以为 $ \epsilon $ 执行此错误。> 0 $。</span><span class="sxs-lookup"><span data-stu-id="73ff9-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="73ff9-116">通过构造运算符指数的序列来生成更准确的近似值，使错误词取消。</span><span class="sxs-lookup"><span data-stu-id="73ff9-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="73ff9-117">最简单的这样的公式（对称 Trotter 公式或 Strang 拆分）采用的格式为 $ $ U_1 （t） = \prod_{j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O （m ^ 3），对于任何 $ \epsilon > 0 $，可以通过选择 $ $r $ 可缩放为 $m ^ {3/2} t ^ {3/2}/\sqrt {\ epsilon} $。</span><span class="sxs-lookup"><span data-stu-id="73ff9-117">The simplest such formula, the symmetric Trotter formula or Strang splitting, takes the form $$ U_1(t) =\prod_{j=1}^m e^{-iH_j t/2}\prod_{j=m}^1 e^{-iH_j t} = e^{-iHt} + O(m^3 t^3), $$ which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="73ff9-118">甚至可以基于 $U _1 $ 来构建高阶 Trotter 公式。</span><span class="sxs-lookup"><span data-stu-id="73ff9-118">Even higher-order Trotter formulas can be constructed based on $U_1$.</span></span>
<span data-ttu-id="73ff9-119">最简单的顺序公式如下所示：最初由 Suzuki： $ $ U_2 （t） = U_1 ^ 2 （s_1t） U_1 （[1-4s_1] t） U_1 ^ 2 （s_1 t） = e ^ {-iHt} + O （m ^ 5t ^ 5），$ $，其中 $s _1 = （4-4 ^ {1/3}） ^{-1}$。</span><span class="sxs-lookup"><span data-stu-id="73ff9-119">The simplest is the following fourth order formula, originally introduced by Suzuki: $$ U_2(t) = U_1^2(s_1t) U_1([1-4s_1]t)U_1^2(s_1 t) = e^{-iHt} +O(m^5t^5), $$ where $s_1 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="73ff9-120">通常，可以按类似方式构造任意高阶公式;然而，使用更复杂的集成商时所产生的成本通常会超出大多数实际问题的第四个订单的权益。</span><span class="sxs-lookup"><span data-stu-id="73ff9-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="73ff9-121">为了使以上策略正常工作，我们需要使用一种方法来模拟 $e ^ {-iH_j t} $ 的种类。</span><span class="sxs-lookup"><span data-stu-id="73ff9-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="73ff9-122">最简单的 Hamiltonians 系列是最有用的，这里我们可以使用 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="73ff9-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="73ff9-123">可以轻松地模拟 Pauli 操作员，因为使用 Clifford 操作（这是量子计算的标准入口）可以 diagonalized。</span><span class="sxs-lookup"><span data-stu-id="73ff9-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="73ff9-124">此外，一旦 diagonalized，就可以通过计算其作用的 qubits 的奇偶校验来找到其本征值。</span><span class="sxs-lookup"><span data-stu-id="73ff9-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="73ff9-125">例如，$ $ e ^ {-iX\otimes X t} = （H\otimes H） e ^ {-iZ\otimes Z t} （H\otimes H），$ $ 其中 $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="73ff9-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="73ff9-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="73ff9-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="73ff9-127">0 & 0 & e ^ {it} & 0 </span><span class="sxs-lookup"><span data-stu-id="73ff9-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="73ff9-128">0 & 0 & 0 & e ^ {\end{bmatrix}.}</span><span class="sxs-lookup"><span data-stu-id="73ff9-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="73ff9-129">$ $ 此处，$e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ and $e ^ {-iHt} \ket{01} = e ^ {-} \ket{01}$，这种结果可以直接查看，因为 $0 $ 的奇偶校验为 $0 $，而位字符串 $1 $ 的奇偶校验为 $1 $。</span><span class="sxs-lookup"><span data-stu-id="73ff9-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="73ff9-130">指数 of Pauli 运算符可在 Q # 中使用 <xref:microsoft.quantum.primitive.exp> 操作直接实现：</span><span class="sxs-lookup"><span data-stu-id="73ff9-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.primitive.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="73ff9-131">对于 Fermionic Hamiltonians，[约旦– Wigner 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner)方便地将 Hamiltonian 映射到 Pauli 运算符之和。</span><span class="sxs-lookup"><span data-stu-id="73ff9-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="73ff9-132">这意味着可以轻松地将上述方法用于模拟化学。</span><span class="sxs-lookup"><span data-stu-id="73ff9-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="73ff9-133">下面只是一个简单的示例，说明了如何在化学中执行这样的模拟，而不是在 Wigner 表示形式中手动循环 Pauli。</span><span class="sxs-lookup"><span data-stu-id="73ff9-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="73ff9-134">我们的起点是 Fermionic Hamiltonian 的[约旦– Wigner 编码](xref:microsoft.quantum.chemistry.concepts.jordanwigner)，以代码形式表示 `JordanWignerEncoding` 类的实例。</span><span class="sxs-lookup"><span data-stu-id="73ff9-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

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

<span data-ttu-id="73ff9-135">Q # 模拟算法可使用的此格式的约旦– Wigner reprsentation 是用户定义的类型 `JordanWignerEncodingData`。</span><span class="sxs-lookup"><span data-stu-id="73ff9-135">This format of the Jordan–Wigner reprsentation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="73ff9-136">在 Q # 中，此格式会传递到一个便利性函数 `TrotterStepOracle`，该函数将使用 Trotter （Suzuki 集成器）除执行所需的其他参数外，返回运算符逼近时间演化。</span><span class="sxs-lookup"><span data-stu-id="73ff9-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="73ff9-137">重要的是，此实现应用了一些优化，其中介绍了如何[使用量程计算机模拟电子结构 Hamiltonians](https://arxiv.org/abs/1001.3855) ，并[改进了用于量程化学的量程算法](https://arxiv.org/abs/1403.1539)来最大程度地减少需要 qubit 旋转，并减少模拟错误。</span><span class="sxs-lookup"><span data-stu-id="73ff9-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="73ff9-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="73ff9-138">Qubitization</span></span>

<span data-ttu-id="73ff9-139">Qubitization 是一种模拟的替代方法，该方法使用量程行走的想法来模拟量子 dynamics。</span><span class="sxs-lookup"><span data-stu-id="73ff9-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="73ff9-140">尽管 qubitization 需要比 Trotter 公式更多的 qubits，但该方法承诺在发展时间和容错范围内实现最佳缩放。</span><span class="sxs-lookup"><span data-stu-id="73ff9-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="73ff9-141">由于这些原因，它成为了一般模拟 Hamiltonian dynamics 和解决电子结构问题的一种更喜欢方法。</span><span class="sxs-lookup"><span data-stu-id="73ff9-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="73ff9-142">从较高层次来看，qubitization 通过以下步骤完成此操作。</span><span class="sxs-lookup"><span data-stu-id="73ff9-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="73ff9-143">首先，为单一和 Hermitian $H _j $ 和 $h _j \ ge $0 $H = \sum_j h_j H_j $。</span><span class="sxs-lookup"><span data-stu-id="73ff9-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="73ff9-144">通过执行一对反射，qubitization 实现等效于 $ $W = e ^ {\pm i \cos ^{-1}（H/| h | _1）}，$ $ 其中 $ | h | _1 = \sum_j | h_j | $ 的运算符。</span><span class="sxs-lookup"><span data-stu-id="73ff9-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="73ff9-145">下一步涉及到将行走操作员的本征值从 $e ^ {i\pm \cos ^{-1}（E_k/| h | _1）} $ 转换，其中 $E _k $ 是 $H $ 到 $e ^ {-本征值 t} $ 的 iE_k。</span><span class="sxs-lookup"><span data-stu-id="73ff9-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="73ff9-146">这可以通过使用各种量程值转换方法（包括[量程信号处理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)）来实现。</span><span class="sxs-lookup"><span data-stu-id="73ff9-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="73ff9-147">或者，如果只需要静态数量（如 Hamiltonian 的地面状态能量），则它后缀将[阶段估算](xref:microsoft.quantum.libraries.characterization)直接应用于 $W $，以通过采用结果的余弦来估算结果中的地面状态。</span><span class="sxs-lookup"><span data-stu-id="73ff9-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="73ff9-148">这一点很重要，因为它允许 spectral 转换执行经典，而不是使用量子单数值转换方法。</span><span class="sxs-lookup"><span data-stu-id="73ff9-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="73ff9-149">在更详细的级别上，qubitization 的实现需要两个为 Hamiltonian 提供接口的子例程。</span><span class="sxs-lookup"><span data-stu-id="73ff9-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="73ff9-150">与 Trotter – Suzuki 方法不同的是，这些子例程不是经典的，它们的实现需要使用对数比基于 Trotter 的模拟更多的 qubits。</span><span class="sxs-lookup"><span data-stu-id="73ff9-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="73ff9-151">Qubitization 使用的第一个量程子例程称为 $ \operatorname{Select} $，并且承诺生成 \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}，\end{equation}，其中每个 $H _j $ 假设为 Hermitian和单一。</span><span class="sxs-lookup"><span data-stu-id="73ff9-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="73ff9-152">虽然这看起来很有限制，但请记住，Pauli 运算符是 Hermitian 的，因此，类似于量子化学模拟的应用程序自然会落到此框架中。</span><span class="sxs-lookup"><span data-stu-id="73ff9-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="73ff9-153">$ \Operatorname{Select} $ 操作（可能令人吃惊）实际上是一个反射操作。</span><span class="sxs-lookup"><span data-stu-id="73ff9-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="73ff9-154">由于每个 $H \ket{\psi} $ 为单一和 _J，因此具有 Hermitian $ 本征值 $1，因此可从 $ \operatorname{Select} ^ 2 \ 票证 {j} \ket{\psi} = \ket{j} \pm $ 这一事实中了解这一点。</span><span class="sxs-lookup"><span data-stu-id="73ff9-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="73ff9-155">第二个子例程称为 $ \operatorname{Prepare} $。</span><span class="sxs-lookup"><span data-stu-id="73ff9-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="73ff9-156">尽管 select 操作提供了一种方法来一致访问每个 Hamiltonian 条款 $H _j $ the prepare 子程序提供了一个方法来访问系数 $h _j $，\begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{| h | _1}} \ket{j}。</span><span class="sxs-lookup"><span data-stu-id="73ff9-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="73ff9-157">\end{equation} 然后，通过使用多重控制的阶段入口，可以看到 $ $ \Lambda\ket{0}^ {\otimes n} = \begin{cases} \-\ket{x} & \text{if} x = 0 </span><span class="sxs-lookup"><span data-stu-id="73ff9-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="73ff9-158">\ket{x} & \text{otherwise} \end{cases}。</span><span class="sxs-lookup"><span data-stu-id="73ff9-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="73ff9-159">$ \Operatorname{Prepare} $ 操作不直接在 qubitization 中使用，而是用于实现有关 $ \operatorname{Prepare} $ 创建 $ $ \begin{align} &amp; R 的状态的反射，即 1-2 \ o {\ket} \bra{0}{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}。</span><span class="sxs-lookup"><span data-stu-id="73ff9-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="73ff9-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="73ff9-160">\end{align} $$</span></span>

<span data-ttu-id="73ff9-161">可以使用 $ \operatorname{Select} $ 和 $R $ 操作数作为 $ $ W = \operatorname{Select} R，$ $ 进行表达运算符 $W $，该操作再次可用于实现等效于 $e ^ {\pm i \cos ^{-1}（H/| H | _1）} $ 的运算符。</span><span class="sxs-lookup"><span data-stu-id="73ff9-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="73ff9-162">可以轻松地在 Q # 中设置这些子例程。</span><span class="sxs-lookup"><span data-stu-id="73ff9-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="73ff9-163">例如，请考虑简单的 qubit Ising Hamiltonian，其中 $H = X_1 + X_2 + Z_1 Z_2 $。</span><span class="sxs-lookup"><span data-stu-id="73ff9-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="73ff9-164">在这种情况下，<xref:microsoft.quantum.canon.multiplexoperations>会调用实现 $ \operatorname{Select} $ 操作的 Q # 代码，而 $ \operatorname{Prepare} $ 操作可以使用 <xref:microsoft.quantum.preparation.preparearbitrarystate>来实现。</span><span class="sxs-lookup"><span data-stu-id="73ff9-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="73ff9-165">涉及模拟 Hubbard 模型的示例可作为[Q # 示例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation)。</span><span class="sxs-lookup"><span data-stu-id="73ff9-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).</span></span>

<span data-ttu-id="73ff9-166">手动为任意化学问题指定这些步骤需要花费很多精力，这可避免使用化学库。</span><span class="sxs-lookup"><span data-stu-id="73ff9-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="73ff9-167">与上面的 Trotter – Suzuki 模拟算法类似，将 `JordanWignerEncodingData` 传递给返回行走运算符的便利函数 `QubitizationOracle`，以及执行所需的其他参数。</span><span class="sxs-lookup"><span data-stu-id="73ff9-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="73ff9-168">重要的是，实现 <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> 适用于指定为 Pauli 字符串的线性组合的任意 Hamiltonians。</span><span class="sxs-lookup"><span data-stu-id="73ff9-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="73ff9-169">使用 <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>调用为化学模拟优化的版本。</span><span class="sxs-lookup"><span data-stu-id="73ff9-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="73ff9-170">此版本经过优化，可将使用[编码电子 Spectra 时所讨论的技术与线性 t 复杂度进行编码](https://arxiv.org/abs/1805.03662)，从而最大程度地减少 T 入口数。</span><span class="sxs-lookup"><span data-stu-id="73ff9-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
