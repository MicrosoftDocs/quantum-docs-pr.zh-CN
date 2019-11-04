---
title: 约旦-Wigner 表示形式 |Microsoft Docs
description: 约旦-Wigner 表示概念文档
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: f34233bc17ff68a9e04256959f8d79be2682c34f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184043"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="c8ef2-103">约旦-Wigner 表示形式</span><span class="sxs-lookup"><span data-stu-id="c8ef2-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="c8ef2-104">尽管第二个量化 Hamiltonians 可根据 $a ^ \dagger $ （创建）和 $a $ （annihilation）来方便地表示，但这些操作不是量子计算机的基本操作。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="c8ef2-105">因此，如果想要在量程计算机上实现它们，则需要将这些操作员映射到可在量程计算机上实现的单一矩阵。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="c8ef2-106">约旦– Wigner 表示形式提供了一个此类地图。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="c8ef2-107">但有些其他类（例如 Bravyi – Kitaev 表示形式）也存在，并有其各自的优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="c8ef2-108">约旦 Wigner 表示形式的主要优点是它的简单性。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="c8ef2-109">约旦 Wigner 表示形式是直接派生的。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="c8ef2-110">回忆一下，状态 $ \ket{0}_j $ 表示自旋 orbital $j $ 为空，$ \ket{1}_j $ 表示其已被占用。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="c8ef2-111">这意味着 qubits 可以自然地存储给定旋转 orbital 的职业。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="c8ef2-112">接下来，我们将 $a ^ \dagger_j \ket{0}_j = \ket{1}_j $ 和 $a ^ \dagger_j \ket{1}_j = $0。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="c8ef2-113">可以轻松验证 \begin{align} a ^ \dagger_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}，\nonumber\\\\ a_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{bmatrix} = \frac{X_j-iY_j}{2}，\end{align}，其中 $X _j $ 和 $Y _j $ 是作用于 Pauli $Y $ 的 $X Qubit $ 和-$j $ 运算符。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>
<span data-ttu-id="c8ef2-114">这表明，对于单个自旋 orbital，可以根据量子计算机可识别的单一矩阵轻松表示创建和 annihilation 运算符。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-114">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="c8ef2-115">请注意，尽管 $X $ 和 $Y $ 是单一 $a ^ \dagger $，但 $a $ 不是。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-115">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="c8ef2-116">稍后我们将会看到，这不会为模拟带来挑战。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-116">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="c8ef2-117">还有一个问题是，尽管上述构造适用于单个自旋 orbital，但对于具有两个或多个自旋 orbitals 的系统，它会失败。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-117">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="c8ef2-118">由于 Fermions 是 antisymmetic 的，因此我们知道 $a ^ \dagger_j a ^ \dagger_k =-a ^ \dagger_k ^ \dagger_j $ 用于任何 $j $ 和 $k $。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-118">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="c8ef2-119">但是，$ $ \left （\frac{X_j-iY_j}{2}\right） \left （\frac{X_k-iY_k}{2}\right） = \left （\frac{X_k-iY_k}{2}\right） \left （\frac{X_j-iY_j}{2}\right）。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-119">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="c8ef2-120">换言之，这两个创建运算符不会根据需要进行反接。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-120">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="c8ef2-121">这可以通过简单的 inelegant 方式来纠正。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-121">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="c8ef2-122">解决方法是注意，Pauli 运算符天生都是反路程。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-122">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="c8ef2-123">具体而言，$XZ =-ZX $ and $YZ =-ZY $。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-123">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="c8ef2-124">因此，通过 interspersing 将 $ operators $Z 为构造运算符，我们可以模拟正确的通信。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-124">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="c8ef2-125">完整的构造如下所示：</span><span class="sxs-lookup"><span data-stu-id="c8ef2-125">The full construction is as follows:</span></span> 

<span data-ttu-id="c8ef2-126">\begin{align} a ^ \dagger_1 & = \left （\frac{X-iY}{2}\right） \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1，\\\\ a ^ \dagger_2 & = Z\otimes\left （\frac{X-iY}{2}\right） \otimes 1 \ otimes 1 \otimes \cdots \otimes 1，\\\\ ^ \dagger_3 & = Z\otimes Z\otimes \left （\frac{X-iY}{2}\right） \otimes 1 \otimes \cdots \otimes 1，\\\\ & \vdots\\\\ ^ \dagger_N & = Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimesZ\otimes \left （\frac{X-iY}{2}\right）。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-126">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="c8ef2-127">\label{eq： JW} \end{align}</span><span class="sxs-lookup"><span data-stu-id="c8ef2-127">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="c8ef2-128">也可以根据 Pauli 运算符来表达数字运算符，$n _j $。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-128">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="c8ef2-129">令人欣慰，$Z $ operators 的字符串（称为 Wigner 字符串）在进行一次替换后取消。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-129">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="c8ef2-130">在执行此项（并再次调用 $X _jY_j = iZ_j $）后，我们已 \begin{equation} n_j = a ^ \dagger_j a_j = \frac{（1-Z_j）}{2}。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-130">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="c8ef2-131">\end{equation}</span><span class="sxs-lookup"><span data-stu-id="c8ef2-131">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="c8ef2-132">构建约旦 Wigner 表示形式的 Hamiltonians</span><span class="sxs-lookup"><span data-stu-id="c8ef2-132">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="c8ef2-133">一旦我们调用了 Wigner 表示形式，则将 Hamiltonian 转换为 Pauli 运算符的总和就是一种直接的方法。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-133">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="c8ef2-134">只需将 Fermionic Hamiltonian 中的每个 $a ^ \dagger $ 和 $a $ 运算符替换为上面给定的 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-134">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="c8ef2-135">当一次执行此替换时，Hamiltonian 中只有五个术语。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-135">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="c8ef2-136">这五个类对应于我们可以选择 $p、q $ 和 $p、q、r、Hamiltonian 中的单正文和两正文术语中的方法的不同方式。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-136">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="c8ef2-137">对于这五个类，如果 $p > q > r > s $ 和实值 orbitals，则会</span><span class="sxs-lookup"><span data-stu-id="c8ef2-137">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="c8ef2-138">\begin{align} h_ {pp} a_p ^ \dagger a_p & = \sum_p \frac{h_{pp}}{2}（1-Z_p）\\\\ h_ {pq} （a_p ^ \dagger a_q + a ^ \dagger_q a_p） & = \frac{h_{pq}}{2}\left （\prod_{j = q + 1} ^ {p-1} Z_j \right） \left （X_pX_q + Y_pY_q\right）\\\\ h_ {pqqp} n_p n_q & = \frac{h_{pqqp}}{4}\left （1-Z_p-Z_q + Z_pZ_q \right）\\\\ H_ {pqqr} & = \frac{h_{pqqr}}{2}\left （\prod_{j =r + 1} ^ {p-1} Z_j \right） \left （X_pX_r + Y_pY_r\right） \left （\frac{1-Z_q}{2}\right）\\\\ H_ {pqrs} & = \frac{h_{pqrs}}{8}\prod_{j = s + 1} ^ {r-1} Z_j\prod_ {k = q + 1} ^ {p-1} Z_k \Big （XXXX-XXYY +XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big） \end{align}</span><span class="sxs-lookup"><span data-stu-id="c8ef2-138">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="c8ef2-139">尽管手动生成此类 Hamiltonians 需要应用这些替换规则，但对于大型分子来说，这种做法不可行，因为这种情况可能包含数百万 Hamiltonian 条款。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-139">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="c8ef2-140">作为替代方法，可以根据 Hamiltonian 的 `FermionHamiltonian` 表示形式自动构造 `JordanWignerEncoding`。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-140">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="c8ef2-141">在此窗体中构造 Hamiltonians 后，我们可以使用一段量程模拟算法将动态 $e 生成的 dynamics 编译为一个基本入口序列（在某些用户可定义的容错范围内）。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-141">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="c8ef2-142">我们在算法文档中讨论了用于量程模拟、qubitization 和 Trotter – Suzuki 公式的两种最常用的方法。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-142">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="c8ef2-143">我们在 Hamiltonian 模拟库中提供了这两种方法的实现。</span><span class="sxs-lookup"><span data-stu-id="c8ef2-143">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>
