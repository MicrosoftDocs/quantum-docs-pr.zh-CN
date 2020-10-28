---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: b7196c592690a00da49b17f52b30536ba97b6035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701085"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="763d8-102">ApplyPermutationUsingTransformation 操作</span><span class="sxs-lookup"><span data-stu-id="763d8-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="763d8-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="763d8-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="763d8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="763d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="763d8-105">使用基于转换的合成，将 amplitudes Permutes 为量程状态。</span><span class="sxs-lookup"><span data-stu-id="763d8-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="763d8-106">说明</span><span class="sxs-lookup"><span data-stu-id="763d8-106">Description</span></span>

<span data-ttu-id="763d8-107">此过程实现基于单向转换的合成方法。</span><span class="sxs-lookup"><span data-stu-id="763d8-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="763d8-108">输入是一种排列 $ \pi $ over $ 2 ^ n $ 元素 $ \{ 0，\dots ..，2 ^ n-1 \} $，表示 $n $-可变可逆布尔函数。</span><span class="sxs-lookup"><span data-stu-id="763d8-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="763d8-109">算法以迭代方式执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="763d8-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="763d8-110">查找 $x \ne \pi (x) = y $ 的最小 $x $。</span><span class="sxs-lookup"><span data-stu-id="763d8-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="763d8-111">查找多个受控制的 Toffoli 操作，这些操作应用于输出使 $ \pi (x) = x $，而不会更改所有 $x < x $ 的 $ \pi (x ' ) $</span><span class="sxs-lookup"><span data-stu-id="763d8-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="763d8-112">输入</span><span class="sxs-lookup"><span data-stu-id="763d8-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="763d8-113">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="763d8-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="763d8-114">从0开始的 $ 2 ^ n $ 元素的排列。</span><span class="sxs-lookup"><span data-stu-id="763d8-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="763d8-115">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="763d8-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="763d8-116">将排列应用到的 $n $ qubits 的列表。</span><span class="sxs-lookup"><span data-stu-id="763d8-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="763d8-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="763d8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="763d8-118">参考</span><span class="sxs-lookup"><span data-stu-id="763d8-118">References</span></span>

- [<span data-ttu-id="763d8-119">*D. Michael 莎莎* ， *Dmitri Maslov* ， *Gerhard DUECK* ，Proc 2003，IEEE，pp 318-323，2003</span><span class="sxs-lookup"><span data-stu-id="763d8-119">*D. Michael Miller* , *Dmitri Maslov* , *Gerhard W. Dueck* , Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="763d8-120">*Mathias Soeken* ， *Gerhard Dueck* ， *d. Michael 莎莎* ，Proc 2016，springer link，pp 307-321，2016</span><span class="sxs-lookup"><span data-stu-id="763d8-120">*Mathias Soeken* , *Gerhard W. Dueck* , *D. Michael Miller* , Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="763d8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="763d8-121">See Also</span></span>

- [<span data-ttu-id="763d8-122">ApplyPermutationUsingDecomposition。</span><span class="sxs-lookup"><span data-stu-id="763d8-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)