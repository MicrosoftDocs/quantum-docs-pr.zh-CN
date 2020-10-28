---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695919"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="fae12-102">TrotterStepSize 函数</span><span class="sxs-lookup"><span data-stu-id="fae12-102">TrotterStepSize function</span></span>

<span data-ttu-id="fae12-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fae12-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fae12-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fae12-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fae12-105">计算 Trotter 模拟算法的递归实现中的 Trotter 步长大小。</span><span class="sxs-lookup"><span data-stu-id="fae12-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="fae12-106">输入</span><span class="sxs-lookup"><span data-stu-id="fae12-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="fae12-107">顺序： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fae12-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="fae12-108">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fae12-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="fae12-109">注解</span><span class="sxs-lookup"><span data-stu-id="fae12-109">Remarks</span></span>

<span data-ttu-id="fae12-110">此操作使用的索引约定不同于 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139)的索引约定。</span><span class="sxs-lookup"><span data-stu-id="fae12-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="fae12-111">特别是，与 `DecomposedIntoTimeStepsCA(_, 4)` quant/0508139 中的标量 $p _2 ( \lambda) $。</span><span class="sxs-lookup"><span data-stu-id="fae12-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>