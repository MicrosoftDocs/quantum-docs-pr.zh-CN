---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203223"
---
# <a name="decomposedon-function"></a><span data-ttu-id="925b8-102">DecomposedOn 函数</span><span class="sxs-lookup"><span data-stu-id="925b8-102">DecomposedOn function</span></span>

<span data-ttu-id="925b8-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="925b8-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="925b8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="925b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="925b8-105">对变量分解</span><span class="sxs-lookup"><span data-stu-id="925b8-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="925b8-106">描述</span><span class="sxs-lookup"><span data-stu-id="925b8-106">Description</span></span>

<span data-ttu-id="925b8-107">给定排列 $ \pi $ (`perm`) ，$i $ () 的索引 `index` ，此方法返回三个排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，以使 $ \ pi_l $ 和 $ \ pi_r $ 的图像不会在其元素中的索引（而不是 $ \pi ' $ 的）中更改其元素中的位。</span><span class="sxs-lookup"><span data-stu-id="925b8-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="925b8-108">输入</span><span class="sxs-lookup"><span data-stu-id="925b8-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="925b8-109">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="925b8-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="925b8-110">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="925b8-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="925b8-111">Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) </span><span class="sxs-lookup"><span data-stu-id="925b8-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

