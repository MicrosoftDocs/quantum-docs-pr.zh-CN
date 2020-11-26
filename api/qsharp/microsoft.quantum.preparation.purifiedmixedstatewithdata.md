---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229947"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="23cb8-102">PurifiedMixedStateWithData 函数</span><span class="sxs-lookup"><span data-stu-id="23cb8-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="23cb8-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="23cb8-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="23cb8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23cb8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23cb8-105">返回一个操作，该操作准备具有给定混合状态的 purification，并使用表示给定数据集合的寄存器放大。</span><span class="sxs-lookup"><span data-stu-id="23cb8-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="23cb8-106">"带有数据的 purified 混合状态" 指的是Σi √ pi | i ⟩ | xi ⟩ | garbagei ⟩格式的状态，其中每个 xi 都是一个 bitstring 编码其他与 register 关联的数据 | i ⟩。</span><span class="sxs-lookup"><span data-stu-id="23cb8-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="23cb8-107"> https://arxiv.org/pdf/1805.03662.pdf?page=15有关进一步的讨论，请参阅。</span><span class="sxs-lookup"><span data-stu-id="23cb8-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="23cb8-108">描述</span><span class="sxs-lookup"><span data-stu-id="23cb8-108">Description</span></span>

<span data-ttu-id="23cb8-109">使用量程 ROM 技术来表示给定密度矩阵，并将该表示形式作为状态准备操作返回。</span><span class="sxs-lookup"><span data-stu-id="23cb8-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="23cb8-110">具体而言，给定 $N $ 系数 $ \ alpha_j $ 的列表和 _与每个系数关联的 bitstring $ \vec{x} j $，此函数返回一个操作，该操作使用量程 ROM 技术来准备近似值 $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ of 混合状态 $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |}{\ sum_k | \ alpha_k |}\ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}，\end{align} $ $，其中的每个 $p _j $ 是给定系数 $ \ alpha_j $ 的近似值，$ $ \begin{align} \left |p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}每个 $j $ 的 \frac{\epsilon}{N} \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="23cb8-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="23cb8-111">传递索引注册和垃圾 qubits 注册时，最初在状态 $ \ket {0} \ket{00\cdots 0} 中，返回的操作准备注册到 $ \tilde \rho $，$ $ \begin{align} \ sum_ {j = 0} ^ {N} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}，\end{align} $ $ 这样的操作，以便在目标错误 $ 制定 $ 中重置和取消分配垃圾寄存器 \epsilon 所需的准备工作。</span><span class="sxs-lookup"><span data-stu-id="23cb8-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="23cb8-112">输入</span><span class="sxs-lookup"><span data-stu-id="23cb8-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="23cb8-113">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="23cb8-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="23cb8-114">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="23cb8-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="23cb8-115">系数： ([Double](xref:microsoft.quantum.lang-ref.double)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) []</span><span class="sxs-lookup"><span data-stu-id="23cb8-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="23cb8-116">$N $ 系数的数组，用于指定基础状态的概率，以及与每个系数关联的 bitstring $ \vec{x} _j $。</span><span class="sxs-lookup"><span data-stu-id="23cb8-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="23cb8-117">负数 $-\ alpha_j $ 将被视为正 $ | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="23cb8-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="23cb8-118">输出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="23cb8-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="23cb8-119">一种操作，用于将 $ \tilde \rho $ 作为 purification 准备到联合索引和垃圾寄存器。</span><span class="sxs-lookup"><span data-stu-id="23cb8-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="23cb8-120">备注</span><span class="sxs-lookup"><span data-stu-id="23cb8-120">Remarks</span></span>

<span data-ttu-id="23cb8-121">为此操作提供的系数按照1个标准进行规范化，以便始终考虑系数来描述有效的分类概率分布。</span><span class="sxs-lookup"><span data-stu-id="23cb8-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="23cb8-122">参考</span><span class="sxs-lookup"><span data-stu-id="23cb8-122">References</span></span>

- <span data-ttu-id="23cb8-123">通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="23cb8-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="23cb8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23cb8-124">See Also</span></span>

- [<span data-ttu-id="23cb8-125">PurifiedMixedState。</span><span class="sxs-lookup"><span data-stu-id="23cb8-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)