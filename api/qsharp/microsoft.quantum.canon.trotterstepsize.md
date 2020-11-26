---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204685"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="c6ac4-102">TrotterStepSize 函数</span><span class="sxs-lookup"><span data-stu-id="c6ac4-102">TrotterStepSize function</span></span>

<span data-ttu-id="c6ac4-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6ac4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6ac4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6ac4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6ac4-105">计算 Trotter 模拟算法的递归实现中的 Trotter 步长大小。</span><span class="sxs-lookup"><span data-stu-id="c6ac4-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="c6ac4-106">输入</span><span class="sxs-lookup"><span data-stu-id="c6ac4-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="c6ac4-107">顺序： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6ac4-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="c6ac4-108">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c6ac4-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="c6ac4-109">备注</span><span class="sxs-lookup"><span data-stu-id="c6ac4-109">Remarks</span></span>

<span data-ttu-id="c6ac4-110">此操作使用的索引约定不同于 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139)的索引约定。</span><span class="sxs-lookup"><span data-stu-id="c6ac4-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="c6ac4-111">特别是，与 `DecomposedIntoTimeStepsCA(_, 4)` quant/0508139 中的标量 $p _2 ( \lambda) $。</span><span class="sxs-lookup"><span data-stu-id="c6ac4-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>