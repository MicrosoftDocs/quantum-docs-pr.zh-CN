---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191034"
---
# <a name="addfxp-operation"></a><span data-ttu-id="e296c-102">AddFxP 操作</span><span class="sxs-lookup"><span data-stu-id="e296c-102">AddFxP operation</span></span>

<span data-ttu-id="e296c-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e296c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e296c-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="e296c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="e296c-105">添加存储在量程寄存器中的两个定点数。</span><span class="sxs-lookup"><span data-stu-id="e296c-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e296c-106">描述</span><span class="sxs-lookup"><span data-stu-id="e296c-106">Description</span></span>

<span data-ttu-id="e296c-107">在状态 $ \ket{f_1} $ 和 $ \ket{f_2} $ 中分别给定了两个定点寄存器，执行操作 $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $。</span><span class="sxs-lookup"><span data-stu-id="e296c-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="e296c-108">输入</span><span class="sxs-lookup"><span data-stu-id="e296c-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="e296c-109">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e296c-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e296c-110">第一个固定点数字</span><span class="sxs-lookup"><span data-stu-id="e296c-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="e296c-111">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e296c-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e296c-112">第二个定点数将被更新，以包含两个输入的和。</span><span class="sxs-lookup"><span data-stu-id="e296c-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e296c-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e296c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e296c-114">备注</span><span class="sxs-lookup"><span data-stu-id="e296c-114">Remarks</span></span>

<span data-ttu-id="e296c-115">当前实现要求两个固定点数字与最小有效位之间具有相同的点位置计数，即 $n _i $，$p _i $ 必须相等。</span><span class="sxs-lookup"><span data-stu-id="e296c-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>