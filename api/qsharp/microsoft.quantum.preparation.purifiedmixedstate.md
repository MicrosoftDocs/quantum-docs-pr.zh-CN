---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854302"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="10c99-102">PurifiedMixedState 函数</span><span class="sxs-lookup"><span data-stu-id="10c99-102">PurifiedMixedState function</span></span>

<span data-ttu-id="10c99-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="10c99-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="10c99-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10c99-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10c99-105">返回一个操作，该操作准备给定混合状态的 purification。</span><span class="sxs-lookup"><span data-stu-id="10c99-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="10c99-106">"Purified mixed state" 是指窗体的状态 | ψ⟩ = Σi √ pi | i ⟩ | garbagei ⟩由系数 {pi} 指定。</span><span class="sxs-lookup"><span data-stu-id="10c99-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="10c99-107">此窗体的状态可以减小到混合状态复数≔ pi | i ⟩⟨ i |通过跟踪 "垃圾" 注册 (即，混合状态在计算基础中是对角的) 。</span><span class="sxs-lookup"><span data-stu-id="10c99-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="10c99-108"> https://arxiv.org/pdf/1805.03662.pdf?page=15有关进一步的讨论，请参阅。</span><span class="sxs-lookup"><span data-stu-id="10c99-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="10c99-109">说明</span><span class="sxs-lookup"><span data-stu-id="10c99-109">Description</span></span>

<span data-ttu-id="10c99-110">使用量程 ROM 技术来表示给定密度矩阵，并将该表示形式作为状态准备操作返回。</span><span class="sxs-lookup"><span data-stu-id="10c99-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="10c99-111">具体而言，给定 $N $ 系数 $ \ alpha_j $ 的列表，此函数返回一个操作，该操作使用量程 ROM 技术来准备近似值 $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ 混合状态 $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |}{\ sum_k | \ alpha_k |}\ket{j}\bra{j}，\end{align} $ $，其中每个 $p _j $ 是给定系数 $ \ alpha_j $ 的近似值，如 $ $ \begin{align} \left |p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}每个 $j $ 的 \frac{\epsilon}{N} \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="10c99-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="10c99-112">传递索引注册和垃圾 qubits 注册时，最初，在状态 $ \ket {0} \ket{00\cdots 0} 中，返回的操作准备注册到 $ \tilde \rho $，$ $ \begin{align} \ sum_ {j = 0} ^ {N} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}，\end{align} $ $ 这样的 purification，以便在目标错误 $ 制定 $ 中重置并解除分配垃圾寄存器 \epsilon 所需的准备工作。</span><span class="sxs-lookup"><span data-stu-id="10c99-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="10c99-113">输入</span><span class="sxs-lookup"><span data-stu-id="10c99-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="10c99-114">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="10c99-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="10c99-115">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="10c99-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="10c99-116">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="10c99-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="10c99-117">$N $ 系数的数组，用于指定基础状态的概率。</span><span class="sxs-lookup"><span data-stu-id="10c99-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="10c99-118">负数 $-\ alpha_j $ 将被视为正 $ | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="10c99-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="10c99-119">输出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="10c99-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="10c99-120">一种操作，用于将 $ \tilde \rho $ 作为 purification 准备到联合索引和垃圾寄存器。</span><span class="sxs-lookup"><span data-stu-id="10c99-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="10c99-121">示例</span><span class="sxs-lookup"><span data-stu-id="10c99-121">Example</span></span>

<span data-ttu-id="10c99-122">下面的代码段准备了 $ 3 $-qubit state $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} 的 purification{\ sum_k | \ alpha_k |}\ket{j}\bra{j} $，其中 $ \vec\alpha = (1.0，2.0，3.0，4.0，5.0) $，目标错误为 $10 ^ {-3} $：</span><span class="sxs-lookup"><span data-stu-id="10c99-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="10c99-123">备注</span><span class="sxs-lookup"><span data-stu-id="10c99-123">Remarks</span></span>

<span data-ttu-id="10c99-124">为此操作提供的系数按照1个标准进行规范化，以便始终考虑系数来描述有效的分类概率分布。</span><span class="sxs-lookup"><span data-stu-id="10c99-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="10c99-125">参考</span><span class="sxs-lookup"><span data-stu-id="10c99-125">References</span></span>

- <span data-ttu-id="10c99-126">通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="10c99-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="10c99-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10c99-127">See Also</span></span>

- [<span data-ttu-id="10c99-128">PurifiedMixedStateWithData。</span><span class="sxs-lookup"><span data-stu-id="10c99-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)