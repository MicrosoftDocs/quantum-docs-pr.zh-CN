---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840072"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="25a46-102">TrotterStepSize 函数</span><span class="sxs-lookup"><span data-stu-id="25a46-102">TrotterStepSize function</span></span>

<span data-ttu-id="25a46-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25a46-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25a46-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25a46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25a46-105">计算 Trotter 模拟算法的递归实现中的 Trotter 步长大小。</span><span class="sxs-lookup"><span data-stu-id="25a46-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="25a46-106">输入</span><span class="sxs-lookup"><span data-stu-id="25a46-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="25a46-107">顺序： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25a46-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="25a46-108">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25a46-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="25a46-109">备注</span><span class="sxs-lookup"><span data-stu-id="25a46-109">Remarks</span></span>

<span data-ttu-id="25a46-110">此操作使用的索引约定不同于 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139)的索引约定。</span><span class="sxs-lookup"><span data-stu-id="25a46-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="25a46-111">特别是，与 `DecomposedIntoTimeStepsCA(_, 4)` quant/0508139 中的标量 $p _2 ( \lambda) $。</span><span class="sxs-lookup"><span data-stu-id="25a46-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>