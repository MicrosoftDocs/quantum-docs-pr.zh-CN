---
title: 电子系统的量程模式 |Microsoft Docs
description: 电子系统概念文档的量程模型
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 45d134333c8a3c8937d206cb0a4a9cc6101a85df
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184145"
---
# <a name="quantum-models-for-electronic-systems"></a><span data-ttu-id="25477-103">适用于电子系统的量程模型</span><span class="sxs-lookup"><span data-stu-id="25477-103">Quantum Models for Electronic Systems</span></span>

<span data-ttu-id="25477-104">为了模拟电子系统，我们需要首先指定 Hamiltonian，这可通过上述规范量化过程来找到。</span><span class="sxs-lookup"><span data-stu-id="25477-104">In order to simulate electronic systems we need to first begin by specifying the Hamiltonian, which can be found by the canonical quantization procedure described above.</span></span>
<span data-ttu-id="25477-105">具体而言，对于 $N _e $ 电子 with momenta $p _i $ （在三个维度中）和大容量 $m _e $ 和位置向量 $x _i $ 和 nuclei，_k $ _k e $ at 位置 $Z Hamiltonian $，\Begin{equation} operator 读取 \hat{H} \Sum = $y {i = 1} ^ {N\__t_1_ e} \frac{\hat{p}\_i ^ 2} {2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_，k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |}+ \frac{1}{2} \sum_{k\ne k '} \frac{Z\_kZ\_{k '} e ^ 2} {| y\_k ' |}。</span><span class="sxs-lookup"><span data-stu-id="25477-105">Specifically, for $N_e$ electrons with momenta $p_i$ (in three dimensions) and mass $m_e$  and position vectors $x_i$ along with nuclei with charges $Z_k e$ at positions $y_k$, the Hamiltonian operator reads \begin{equation} \hat{H}= \sum\_{i=1}^{N\_e} \frac{\hat{p}\_i^2}{2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e^2}{|\hat{x}\_i - \hat{x}\_j|} -\sum\_{i,k} \frac{Z\_ke^2}{|\hat{x}\_i - {y}\_k|}+\frac{1}{2} \sum_{k\ne k'} \frac{Z\_kZ\_{k'}e^2}{|y\_k - y\_k'|}.</span></span> <span data-ttu-id="25477-106">\label{eq： Ham} \end{equation} momenta 运算符 $ \hat{p}\_i ^ 2 $ 可以作为 Laplacian 运算符在实际空间中查看，即 $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $。</span><span class="sxs-lookup"><span data-stu-id="25477-106">\label{eq:Ham} \end{equation} The momenta operators $\hat{p}\_i^2$ can be viewed in real space as Laplacian operators, i.e. $\hat{p}\_i^2 = -\partial\_{x\_i}^2 - \partial\_{y\_i}^2 - \partial\_{z\_i}^2$.</span></span>
<span data-ttu-id="25477-107">在这里，我们已简化了分子的 nuclei。</span><span class="sxs-lookup"><span data-stu-id="25477-107">Here we have made the simplifying assumption that the nuclei are at rest for the molecule.</span></span>
<span data-ttu-id="25477-108">这称为 "Oppenheimer" 近似值，它往往适用于 $ \hat{H} $ 的低能耗能量，因为 electron 质量约为 $ 1/1836 $ proton 的质量。</span><span class="sxs-lookup"><span data-stu-id="25477-108">This is known as the Born-Oppenheimer approximation and it tends to be valid for the low-energy energy spectrum of $\hat{H}$ since the electron mass is about $1/1836$ the mass of a proton.</span></span>
<span data-ttu-id="25477-109">可以通过 $N\_e $ 电子的系统的能耗 e $ 和应用[量程](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)中所述的规范量化过程，轻松找到此 Hamiltonian 运算符。</span><span class="sxs-lookup"><span data-stu-id="25477-109">This Hamiltonian operator can be easily found by writing out the energy for a system of $N\_e$ electrons and applying the canonical quantization process described in [Quantum Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).</span></span>

<span data-ttu-id="25477-110">为了构造 $e ^ {-i\hat {H} t} $ 的单一矩阵表示形式，我们需要将运算符 $ \hat{H} $ 表示为矩阵。</span><span class="sxs-lookup"><span data-stu-id="25477-110">In order to construct the unitary matrix representation for $e^{-i\hat{H} t}$ we need to represent the operator $\hat{H}$ as a matrix.</span></span>
<span data-ttu-id="25477-111">为此，我们需要选择一个坐标系统或基础来表示中的问题。</span><span class="sxs-lookup"><span data-stu-id="25477-111">For this, we need to choose a coordinate system or basis to represent the problem in.</span></span>
<span data-ttu-id="25477-112">例如，如果 $ \psi_j $ 是 $N _e $ 电子的一组正交基数函数，则可以定义矩阵</span><span class="sxs-lookup"><span data-stu-id="25477-112">For example, if $\psi_j$ are a set of orthogonal basis functions for the $N_e$ electrons then we can define the matrix</span></span>

<span data-ttu-id="25477-113">\begin{equation} H\_{i，j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \psi ^ {\*}\_i （x\_1） \hat{H} \psi\_j （x\_2） \dd ^ 3\_1 \dd ^ 3\_2. \ 标签 {eq： discreteHam} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="25477-113">\begin{equation} H\_{i,j} = \int\_{-\infty}^\infty\int\_{-\infty}^\infty \psi^{\*}\_i(x\_1) \hat{H} \psi\_j(x\_2) \dd^3x\_1 \dd^3x\_2.\label{eq:discreteHam} \end{equation}</span></span>

<span data-ttu-id="25477-114">尽管在原则上，运算符 $ \hat{H} $ 是未绑定的，且不会作用于有限的维度空间，但带有元素的矩阵 $H\_\{i，j\}$ 以上。</span><span class="sxs-lookup"><span data-stu-id="25477-114">While in principle the operator $\hat{H}$ is unbounded and does not act on a finite dimensional space, the matrix with elements $H\_\{i,j\}$ above does.</span></span>
<span data-ttu-id="25477-115">这意味着，如果在基本设置中选取太小，则会产生错误;但是，选取一种较大的基础可以模拟化学 dynamics 不切实际。</span><span class="sxs-lookup"><span data-stu-id="25477-115">This means that errors are incurred by picking too small of a basis set; however, picking a large basis can make simulating the chemical dynamics impractical.</span></span>
<span data-ttu-id="25477-116">出于此原因，选择可简明地表示问题的基数对于解决电子结构问题至关重要。</span><span class="sxs-lookup"><span data-stu-id="25477-116">For this reason, choosing a basis that can concisely represent the problem is vital for solving the electronic structure problem.</span></span>

<span data-ttu-id="25477-117">可以使用许多合适的基准，并选择适当的基础来适应问题，这是量程化学的一大优点。</span><span class="sxs-lookup"><span data-stu-id="25477-117">There are many appropriate bases that can be used and the choice of a good basis to fit the problem is much of the art of quantum chemistry.</span></span>
<span data-ttu-id="25477-118">最简单的这种基本设置可能是 Slater Orbitals （停止），这是针对类似于 Schrödinger 的原子的 Eigenfunctions 公式（即，\hat{H} $ hydrogen $）的（orthogonalized）解决方案。</span><span class="sxs-lookup"><span data-stu-id="25477-118">Perhaps the simplest such basis sets are Slater-Type-Orbitals (STO) which are (orthogonalized) solutions to the Schrödinger equation (i.e. eigenfunctions of $\hat{H}$) for hydrogen-like atoms.</span></span>
<span data-ttu-id="25477-119">可以使用其他基础集（如平面-波浪或实空格 orbitals），更详细地说，我们将好奇的读者称为标准文本["分子电子结构理论"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572)的 Helgaker。</span><span class="sxs-lookup"><span data-stu-id="25477-119">Other basis sets, such as plane-waves or real-space orbitals, can be used and for more detail we refer the curious reader to the standard text ['Molecular Electronic-Structure Theory'](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) by Helgaker.</span></span>

<span data-ttu-id="25477-120">虽然以上模型中使用的状态看起来可能是任意的，但量程机制对可在本质上发现的状态施加限制。</span><span class="sxs-lookup"><span data-stu-id="25477-120">While the states used in the above model may seem arbitrary, quantum mechanics places restrictions on the states that can be found in nature.</span></span>
<span data-ttu-id="25477-121">特别是，在 electron 标签的交换下，所有有效的电子量程状态都必须是反对称状态。</span><span class="sxs-lookup"><span data-stu-id="25477-121">In particular, all valid electronic quantum states must be anti-symmetric under exchange of electron labels.</span></span>
<span data-ttu-id="25477-122">也就是说，如果 $ \psi （x_1，x_2） $ 是两个电子的联合量程状态的波形函数，则必须具有 $ $ \psi （x_1，x_2） =-\psi （x_2，x_1）。</span><span class="sxs-lookup"><span data-stu-id="25477-122">That is to say if $\psi(x_1,x_2)$ were the wave function for the joint quantum state of two electrons then we must have that $$ \psi(x_1,x_2)= - \psi(x_2,x_1).</span></span>
<span data-ttu-id="25477-123">$ $ Pauli 排除原则，它禁止两个电子处于相同的量程状态，fascinatingly，这一法律的直接后果是，这是因为我们交换了两个位于同一位置 $ 电子（\psi，x_1） x_1 \mapsto 的 \psi （x_1，x_1） \ne-\psi （x_1，x_1） $，除非 $ \psi （x_1，x_1） = 0 $。</span><span class="sxs-lookup"><span data-stu-id="25477-123">$$ The Pauli exclusion principle which forbids two electrons to ever be in the same quantum state is, fascinatingly, a direct consequence of this law as can be intuited from the fact that if we swap two electrons located at the same position $\psi(x_1,x_1)\mapsto \psi(x_1,x_1) \ne -\psi(x_1,x_1)$ unless $\psi(x_1,x_1)=0$.</span></span>
<span data-ttu-id="25477-124">因此，必须将初始状态选为遵循这种抗对称属性，而不会同时使两个电子处于相同状态。</span><span class="sxs-lookup"><span data-stu-id="25477-124">Thus the initial states must be chosen to obey this anti-symmetry property and in turn never have two electrons in the same state at the same time.</span></span>
<span data-ttu-id="25477-125">这对电子结构至关重要，因为它禁止多个电子处于相同的状态，进而允许量子计算机使用单个量程位来存储给定量程状态下的电子数。</span><span class="sxs-lookup"><span data-stu-id="25477-125">This is crucial for electronic structure because it forbids multiple electrons from being in the same state, and in turn allows quantum computers to use a single quantum bit to store the number of electrons in a given quantum state.</span></span>

<span data-ttu-id="25477-126">尽管量程机制可以通过离散化这些状态在量程计算机上模拟，但该字段中的大部分工作都 eschewed 这种方法，因为它需要许多 qubits 来存储状态，并需要一个复杂的状态准备过程来准备反对称初始状态。</span><span class="sxs-lookup"><span data-stu-id="25477-126">While quantum mechanics can be simulated on a quantum computer by discretizing these states, most work in the field has eschewed this approach because it requires many qubits to store the states and needs a complicated state preparation procedure to prepare an anti-symmetric initial state.</span></span>
<span data-ttu-id="25477-127">幸运的是，这些问题可以通过从不同的角度查看模拟问题来 sidestepped。</span><span class="sxs-lookup"><span data-stu-id="25477-127">Fortunately though, these problems can be sidestepped by viewing the simulation problem from a different perspective.</span></span>