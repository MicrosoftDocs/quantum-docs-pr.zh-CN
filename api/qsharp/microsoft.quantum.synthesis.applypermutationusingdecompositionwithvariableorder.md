---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701088"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="b7f73-102">ApplyPermutationUsingDecompositionWithVariableOrder 操作</span><span class="sxs-lookup"><span data-stu-id="b7f73-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="b7f73-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b7f73-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b7f73-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7f73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7f73-105">使用基于分解的合成，Permutes amplitudes 在量程状态中。</span><span class="sxs-lookup"><span data-stu-id="b7f73-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="b7f73-106">说明</span><span class="sxs-lookup"><span data-stu-id="b7f73-106">Description</span></span>

<span data-ttu-id="b7f73-107">此操作是 @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 可在其中指定可变顺序的更通用版本。</span><span class="sxs-lookup"><span data-stu-id="b7f73-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="b7f73-108">不同的变量顺序将更改分解序列和用于受控入口的事实数据表 @"microsoft.quantum.intrinsic.x" 。</span><span class="sxs-lookup"><span data-stu-id="b7f73-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="b7f73-109">因此，更改可变顺序会改变用于实现排列的总入口数。</span><span class="sxs-lookup"><span data-stu-id="b7f73-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="b7f73-110">输入</span><span class="sxs-lookup"><span data-stu-id="b7f73-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="b7f73-111">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b7f73-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b7f73-112">从0开始的 $ 2 ^ n $ 元素的排列。</span><span class="sxs-lookup"><span data-stu-id="b7f73-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="b7f73-113">variableOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b7f73-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b7f73-114">从0开始 $n $ 元素的排列。</span><span class="sxs-lookup"><span data-stu-id="b7f73-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="b7f73-115">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b7f73-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b7f73-116">将排列应用到的 $n $ qubits 的列表。</span><span class="sxs-lookup"><span data-stu-id="b7f73-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7f73-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7f73-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b7f73-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7f73-118">See Also</span></span>

- [<span data-ttu-id="b7f73-119">ApplyPermutationUsingDecomposition。</span><span class="sxs-lookup"><span data-stu-id="b7f73-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="b7f73-120">ApplyPermutationUsingTransformation。</span><span class="sxs-lookup"><span data-stu-id="b7f73-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)