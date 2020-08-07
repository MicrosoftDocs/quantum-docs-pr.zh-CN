---
title: Hartree-Fock 理论
description: 了解 Hartree – Fock 理论，它是一种简单的方法来构造量程系统的初始状态。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2d5e597c36f7873dfd1e011e7ce7d4b01c0f786e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869538"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="0df6a-103">Hartree – Fock 理论</span><span class="sxs-lookup"><span data-stu-id="0df6a-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="0df6a-104">在量程化学模拟中，最重要的数量或许是地面状态，即 Hamiltonian 矩阵的最小能量 eigenvector。</span><span class="sxs-lookup"><span data-stu-id="0df6a-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="0df6a-105">这是因为，对房间温度的大多数分子（例如，反应速率）由描述反应通道中某个步骤的开始和结束时间的量程状态和房间温度（如中间状态）中的可用能量差异构成。</span><span class="sxs-lookup"><span data-stu-id="0df6a-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="0df6a-106">尽管地面状态通常太难了解 (即使是使用量程计算机) ，因为它是通过指数量大的配置进行分布的。</span><span class="sxs-lookup"><span data-stu-id="0df6a-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="0df6a-107">可以了解地面状态的能源。</span><span class="sxs-lookup"><span data-stu-id="0df6a-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="0df6a-108">例如，如果 $ \ket{\psi} $ 是任何纯量子状态，则 \begin{equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{equation} 提供系统处于该状态的平均能量。</span><span class="sxs-lookup"><span data-stu-id="0df6a-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="0df6a-109">而地面状态则为提供最小此类值的状态。</span><span class="sxs-lookup"><span data-stu-id="0df6a-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="0df6a-110">因此，选择尽可能接近真实状态的状态对于估算能源非常重要，如直接 (在 variational eigensolvers) 或阶段估算中所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="0df6a-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="0df6a-111">Hartree – Fock 理论提供一种简单的方法来构造量程系统的初始状态。</span><span class="sxs-lookup"><span data-stu-id="0df6a-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="0df6a-112">它将对量程系统的基本状态产生单个 Slater 决定。</span><span class="sxs-lookup"><span data-stu-id="0df6a-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="0df6a-113">为此，它在 Fock 范围内找到一个可最大程度地减少地面能耗的旋转。</span><span class="sxs-lookup"><span data-stu-id="0df6a-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="0df6a-114">具体而言，对于 $N $ 电子的系统，该方法执行旋转 \begin{equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket \mapsto \ {0} prod_ {j = 0} ^ {n-1} e ^ {u} \ket \defeq\ { {0} j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket，dagger_j {0} prod_ \End{equation} 与反 Hermitian (，即 $u =-u ^ \dagger $) matrix $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $。</span><span class="sxs-lookup"><span data-stu-id="0df6a-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="0df6a-115">应注意的是，矩阵 $u $ 表示 orbital 旋转，$ \widetilde{a} ^ \ dagger_j $ 和 $ \widetilde{a} _j $ 表示电子占用 Hartree – Fock 分子 orbitals 的创建和 annihilation 运算符。</span><span class="sxs-lookup"><span data-stu-id="0df6a-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="0df6a-116">然后优化矩阵 $u $，以最大程度地减少预期能量 $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="0df6a-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="0df6a-117">虽然这种优化问题可能会很难，但实际上，Hartree – Fock 算法常常会迅速汇聚到优化问题的近乎最佳解决方案，尤其是对于平衡几何图形中的封闭式 shell 分子。</span><span class="sxs-lookup"><span data-stu-id="0df6a-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="0df6a-118">我们可以将这些状态指定为对象的实例 `FermionWavefunction` 。</span><span class="sxs-lookup"><span data-stu-id="0df6a-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="0df6a-119">例如，状态 $a ^ \ dagger_ ^ \ {1} dagger_ {2} 在 {6} {0} 化学库中实例化 ^ \ dagger_ \ket $，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0df6a-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="0df6a-120">还可以用索引为波形函数建立索引 `SpinOrbital` ，然后将这些索引转换为整数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0df6a-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="0df6a-121">关于 Hartree 的最重要的功能-Fock 理论是，它生成的量程状态在电子之间没有牵连。</span><span class="sxs-lookup"><span data-stu-id="0df6a-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="0df6a-122">这意味着，它通常提供分子系统属性的合适定性说明。</span><span class="sxs-lookup"><span data-stu-id="0df6a-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="0df6a-123">还可以从中重新构造 Hartree Fock 状态 `FermionHamiltonian` ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0df6a-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="0df6a-124">但是，若要获得准确的结果，尤其是对于强关联系统，一定要有超过 Hartree – Fock 理论的量程状态。</span><span class="sxs-lookup"><span data-stu-id="0df6a-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
