---
title: 约旦-Wigner 表示形式
description: 了解 Wigner 表示形式，它将 Hamiltonian 运算符映射到可以更轻松地在量程计算机上实现的单一矩阵。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833857"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="4f798-103">约旦-Wigner 表示形式</span><span class="sxs-lookup"><span data-stu-id="4f798-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="4f798-104">尽管第二个量化 Hamiltonians 可根据 $a ^ \dagger $ (创建来方便地表示) 并 $a $ (annihilation) ，但这些操作不是量子计算机的基本操作。</span><span class="sxs-lookup"><span data-stu-id="4f798-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="4f798-105">因此，如果想要在量程计算机上实现它们，则需要将这些操作员映射到可在量程计算机上实现的单一矩阵。</span><span class="sxs-lookup"><span data-stu-id="4f798-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="4f798-106">约旦– Wigner 表示形式提供了一个此类地图。</span><span class="sxs-lookup"><span data-stu-id="4f798-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="4f798-107">但有些其他类（例如 Bravyi – Kitaev 表示形式）也存在，并有其各自的优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="4f798-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="4f798-108">约旦 Wigner 表示形式的主要优点是它的简单性。</span><span class="sxs-lookup"><span data-stu-id="4f798-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="4f798-109">约旦 Wigner 表示形式是直接派生的。</span><span class="sxs-lookup"><span data-stu-id="4f798-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="4f798-110">回忆一下，状态 $ \ket {0} _j $ 表示自旋 orbital $j $ 为空，$ \ket {1} _j $ 表示其已被占用。</span><span class="sxs-lookup"><span data-stu-id="4f798-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="4f798-111">这意味着 qubits 可以自然地存储给定旋转 orbital 的职业。</span><span class="sxs-lookup"><span data-stu-id="4f798-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="4f798-112">接下来，我们将 $a ^ \ dagger_j \ket {0} _j = \ket {1} _j $ 和 $a ^ \ dagger_j \ket {1} _j = $0。</span><span class="sxs-lookup"><span data-stu-id="4f798-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="4f798-113">可以轻松验证 \begin{align} 为 ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j} {2} ，\nonumber \\ \\ iY_j a_j = \begin{bmatrix}0 &1 \\ \ 0 & 0 \end{bmatrix} = \frac{&+ X_j} {2} ，\end{align} 其中 iY_j $X $ 和 _j $Y $ 是 Pauli _j $ $X $ $Y $ 运算符。</span><span class="sxs-lookup"><span data-stu-id="4f798-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>

>[!NOTE]
> <span data-ttu-id="4f798-114">在 Q# $ \ket {0} $ state 中，表示 $Z $ operator 的 + 1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="4f798-114">In Q# the $\ket{0}$ state represents the +1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="4f798-115">在物理学 $ \ket $ 的某些区域中， {0} 它表示低能耗状态，因此是 $Z $ operator 的-1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="4f798-115">In some areas of physics $\ket{0}$ represents the low-energy ground state and thus the -1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="4f798-116">因此，某些公式可能与常用的文献有所不同。</span><span class="sxs-lookup"><span data-stu-id="4f798-116">Therefore some formulas might differ from popular literature.</span></span>

<span data-ttu-id="4f798-117">在化学库中，我们使用 $ \ket {0} $ 来表示未占用的 orbital。</span><span class="sxs-lookup"><span data-stu-id="4f798-117">In the chemistry library we use $\ket{0}$ to represent an unoccupied spin-orbital.</span></span>
<span data-ttu-id="4f798-118">这表明，对于单个自旋 orbital，可以根据量子计算机可识别的单一矩阵轻松表示创建和 annihilation 运算符。</span><span class="sxs-lookup"><span data-stu-id="4f798-118">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="4f798-119">请注意，尽管 $X $ 和 $Y $ 是单一 $a ^ \dagger $，但 $a $ 不是。</span><span class="sxs-lookup"><span data-stu-id="4f798-119">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="4f798-120">稍后我们将会看到，这不会为模拟带来挑战。</span><span class="sxs-lookup"><span data-stu-id="4f798-120">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="4f798-121">还有一个问题是，尽管上述构造适用于单个自旋 orbital，但对于具有两个或多个自旋 orbitals 的系统，它会失败。</span><span class="sxs-lookup"><span data-stu-id="4f798-121">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="4f798-122">由于 Fermions 是 antisymmetic 的，因此，我们知道 $a ^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k ^ \ dagger_j $ 用于任何 $j $ 和 $k $。</span><span class="sxs-lookup"><span data-stu-id="4f798-122">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="4f798-123">但是，$ $ \left ( \frac{X_j-iY_j} {2} \right) \left ( \frac{X_k-iY_k} {2} \right) = \left ( \frac{X_k-iY_k} {2} \right) \left ( \frac{X_j iY_j} {2} \right) 。</span><span class="sxs-lookup"><span data-stu-id="4f798-123">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="4f798-124">换言之，这两个创建运算符不会根据需要进行反接。</span><span class="sxs-lookup"><span data-stu-id="4f798-124">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="4f798-125">这可以通过简单的 inelegant 方式来纠正。</span><span class="sxs-lookup"><span data-stu-id="4f798-125">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="4f798-126">解决方法是注意，Pauli 运算符天生都是反路程。</span><span class="sxs-lookup"><span data-stu-id="4f798-126">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="4f798-127">具体而言，$XZ =-ZX $ and $YZ =-ZY $。</span><span class="sxs-lookup"><span data-stu-id="4f798-127">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="4f798-128">因此，通过 interspersing 将 $ operators $Z 为构造运算符，我们可以模拟正确的通信。</span><span class="sxs-lookup"><span data-stu-id="4f798-128">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="4f798-129">完整的构造如下所示：</span><span class="sxs-lookup"><span data-stu-id="4f798-129">The full construction is as follows:</span></span> 

<span data-ttu-id="4f798-130">\begin{align} ^ \ dagger_1 &= \left ( \frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1， \\ \\ ^ \ dagger_2 &= Z\otimes\left ( \frac{x-iy} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1， \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left ( \frac{x-iy} {2} \right) \otimes 1 \otimes \cdots \otimes 1， \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left ( \frac{x-iy} {2} \right) 。</span><span class="sxs-lookup"><span data-stu-id="4f798-130">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="4f798-131">\label{eq： JW} \end{align}</span><span class="sxs-lookup"><span data-stu-id="4f798-131">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="4f798-132">也可以根据 Pauli 运算符来表达数字运算符，$n _j $。</span><span class="sxs-lookup"><span data-stu-id="4f798-132">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="4f798-133">令人欣慰，$Z $ operators 的字符串 (称为 Wigner 字符串，) 在进行一项替换后取消。</span><span class="sxs-lookup"><span data-stu-id="4f798-133">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="4f798-134">在执行此 (并撤回 $X _jY_j = iZ_j $) 的情况下，我们的 \begin{equation} n_j = a ^ \ dagger_j a_j = \frac{ (1-Z_j) } {2} 。</span><span class="sxs-lookup"><span data-stu-id="4f798-134">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="4f798-135">\end{equation}</span><span class="sxs-lookup"><span data-stu-id="4f798-135">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="4f798-136">构建约旦 Wigner 表示形式的 Hamiltonians</span><span class="sxs-lookup"><span data-stu-id="4f798-136">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="4f798-137">一旦我们调用了 Wigner 表示形式，则将 Hamiltonian 转换为 Pauli 运算符的总和就是一种直接的方法。</span><span class="sxs-lookup"><span data-stu-id="4f798-137">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="4f798-138">只需将 Fermionic Hamiltonian 中的每个 $a ^ \dagger $ 和 $a $ 运算符替换为上面给定的 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="4f798-138">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="4f798-139">当一次执行此替换时，Hamiltonian 中只有五个术语。</span><span class="sxs-lookup"><span data-stu-id="4f798-139">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="4f798-140">这五个类对应于我们可以选择 $p、q $ 和 $p、q、r、Hamiltonian 中的单正文和两正文术语中的方法的不同方式。</span><span class="sxs-lookup"><span data-stu-id="4f798-140">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="4f798-141">对于这五个类，如果 $p>q>r>s $ 和实值 orbitals，则会</span><span class="sxs-lookup"><span data-stu-id="4f798-141">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="4f798-142">\begin{align} h_ {pp} a_p ^ \dagger a_p &= \ sum_p \frac{h_ {pp}} {2} (Z_p \\ \\ ^ \dagger) + a ^ \ h_ (a_p a_q = \frac{dagger_q {pq}} {2} \left a_p \) {j = q + 1} ^ {p-1} Z_j \right) \left ( X_pX_q + Y_pY_q \right) h_ \\ \\ {pqqp} n_p n_q &= \frac{h_ {pqqp}} {4} \left (Z_p Z_q \\ \\ = \frac{h_ {pqqr}} {2} \left ( \ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left ( X_pX_r + Y_pY_r \right) \left ( \frac{1-Z_q} {2} \right) \\ \\ H_ {pqrs} &= \frac{h_ {pqrs}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}</span><span class="sxs-lookup"><span data-stu-id="4f798-142">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="4f798-143">尽管手动生成此类 Hamiltonians 需要应用这些替换规则，但对于大型分子来说，这种做法不可行，因为这种情况可能包含数百万 Hamiltonian 条款。</span><span class="sxs-lookup"><span data-stu-id="4f798-143">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="4f798-144">作为替代方法，我们可以自动构造 `JordanWignerEncoding` 给定 Hamiltonian 的 `FermionHamiltonian` 表示形式。</span><span class="sxs-lookup"><span data-stu-id="4f798-144">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="4f798-145">在此窗体中构造 Hamiltonians 后，我们可以使用一系列量程模拟算法将 $e ^ {-iHt} $ 生成的 dynamics 编译为某些用户可定义的容错) 中 (的基本入口。</span><span class="sxs-lookup"><span data-stu-id="4f798-145">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="4f798-146">我们在算法文档中讨论了用于量程模拟、qubitization 和 Trotter – Suzuki 公式的两种最常用的方法。</span><span class="sxs-lookup"><span data-stu-id="4f798-146">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="4f798-147">我们在 Hamiltonian 模拟库中提供了这两种方法的实现。</span><span class="sxs-lookup"><span data-stu-id="4f798-147">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>
