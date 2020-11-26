---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203427"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="404bb-102">ApplyPermutationUsingDecompositionWithVariableOrder 操作</span><span class="sxs-lookup"><span data-stu-id="404bb-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="404bb-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="404bb-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="404bb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="404bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="404bb-105">使用基于分解的合成，Permutes amplitudes 在量程状态中。</span><span class="sxs-lookup"><span data-stu-id="404bb-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="404bb-106">描述</span><span class="sxs-lookup"><span data-stu-id="404bb-106">Description</span></span>

<span data-ttu-id="404bb-107">此操作是 @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 可在其中指定可变顺序的更通用版本。</span><span class="sxs-lookup"><span data-stu-id="404bb-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="404bb-108">不同的变量顺序将更改分解序列和用于受控入口的事实数据表 @"microsoft.quantum.intrinsic.x" 。</span><span class="sxs-lookup"><span data-stu-id="404bb-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="404bb-109">因此，更改可变顺序会改变用于实现排列的总入口数。</span><span class="sxs-lookup"><span data-stu-id="404bb-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="404bb-110">输入</span><span class="sxs-lookup"><span data-stu-id="404bb-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="404bb-111">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="404bb-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="404bb-112">从0开始的 $ 2 ^ n $ 元素的排列。</span><span class="sxs-lookup"><span data-stu-id="404bb-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="404bb-113">variableOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="404bb-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="404bb-114">从0开始 $n $ 元素的排列。</span><span class="sxs-lookup"><span data-stu-id="404bb-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="404bb-115">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="404bb-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="404bb-116">将排列应用到的 $n $ qubits 的列表。</span><span class="sxs-lookup"><span data-stu-id="404bb-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="404bb-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="404bb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="404bb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="404bb-118">See Also</span></span>

- [<span data-ttu-id="404bb-119">ApplyPermutationUsingDecomposition。</span><span class="sxs-lookup"><span data-stu-id="404bb-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="404bb-120">ApplyPermutationUsingTransformation。</span><span class="sxs-lookup"><span data-stu-id="404bb-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)