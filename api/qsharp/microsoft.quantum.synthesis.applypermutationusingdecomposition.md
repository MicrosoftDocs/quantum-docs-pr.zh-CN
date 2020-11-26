---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 5b25ef3327bbca2dfdbe8fa876f3f797dddf77e8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192122"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="6fd14-102">ApplyPermutationUsingDecomposition 操作</span><span class="sxs-lookup"><span data-stu-id="6fd14-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="6fd14-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6fd14-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6fd14-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fd14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fd14-105">使用基于分解的合成，Permutes amplitudes 在量程状态中。</span><span class="sxs-lookup"><span data-stu-id="6fd14-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6fd14-106">描述</span><span class="sxs-lookup"><span data-stu-id="6fd14-106">Description</span></span>

<span data-ttu-id="6fd14-107">此过程实现基于分解的合成方法。</span><span class="sxs-lookup"><span data-stu-id="6fd14-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="6fd14-108">输入是一种排列 $ \pi $ over $ 2 ^ n $ 元素 $ \{ 0，\dots ..，2 ^ n-1 \} $，表示 $n $-可变可逆布尔函数。</span><span class="sxs-lookup"><span data-stu-id="6fd14-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="6fd14-109">算法会对每个可变索引 $i $ 执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6fd14-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="6fd14-110">计算 $ ( # A1 \ pi_l，\ pi_r) ，\pi ' ) $，以便 $ \ pi_l $ 和 $ \ pi_r $ 的图像在其元素中的索引（而不是 $ \pi ' $ 的索引）上更改其元素中的位。</span><span class="sxs-lookup"><span data-stu-id="6fd14-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="6fd14-111">设置 $ \pi \leftarrow \pi ' $，并基于不是固定点的元素 pi_r $ pi_l 中派生事实数据表。</span><span class="sxs-lookup"><span data-stu-id="6fd14-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="6fd14-112">将这些步骤应用于所有变量索引后，剩余的排列 $ \pi $ 将是标识，基于收集的事实数据表和索引，可以使用操作来应用事实数据表控制的 @"microsoft.quantum.intrinsic.x" 操作 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" 。</span><span class="sxs-lookup"><span data-stu-id="6fd14-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="6fd14-113">变量顺序为 $0、\dots ..、n-$1。</span><span class="sxs-lookup"><span data-stu-id="6fd14-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="6fd14-114">可以在操作中指定自定义变量顺序 @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" 。</span><span class="sxs-lookup"><span data-stu-id="6fd14-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="6fd14-115">输入</span><span class="sxs-lookup"><span data-stu-id="6fd14-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="6fd14-116">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6fd14-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6fd14-117">从0开始的 $ 2 ^ n $ 元素的排列。</span><span class="sxs-lookup"><span data-stu-id="6fd14-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6fd14-118">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6fd14-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6fd14-119">将排列应用到的 $n $ qubits 的列表。</span><span class="sxs-lookup"><span data-stu-id="6fd14-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6fd14-120">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fd14-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="6fd14-121">参考</span><span class="sxs-lookup"><span data-stu-id="6fd14-121">References</span></span>

- [<span data-ttu-id="6fd14-122">*Alexis De Vos*， *Yvan Van Rentergem*，高级. 2 (2) ，2008，pp 183--200</span><span class="sxs-lookup"><span data-stu-id="6fd14-122">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="6fd14-123">*Mathias Soeken*、 *刘娜 Tague*、 *Gerhard Dueck*、 *Rolf Drechsler*、) 符号计算 73 (2016、pp 1--26</span><span class="sxs-lookup"><span data-stu-id="6fd14-123">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="6fd14-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fd14-124">See Also</span></span>

- [<span data-ttu-id="6fd14-125">ApplyPermutationUsingDecompositionWithVariableOrder。</span><span class="sxs-lookup"><span data-stu-id="6fd14-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="6fd14-126">ApplyPermutationUsingTransformation。</span><span class="sxs-lookup"><span data-stu-id="6fd14-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)