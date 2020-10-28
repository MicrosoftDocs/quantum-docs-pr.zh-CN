---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700060"
---
# <a name="addfxp-operation"></a><span data-ttu-id="ccc51-102">AddFxP 操作</span><span class="sxs-lookup"><span data-stu-id="ccc51-102">AddFxP operation</span></span>

<span data-ttu-id="ccc51-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ccc51-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ccc51-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ccc51-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ccc51-105">添加存储在量程寄存器中的两个定点数。</span><span class="sxs-lookup"><span data-stu-id="ccc51-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="ccc51-106">说明</span><span class="sxs-lookup"><span data-stu-id="ccc51-106">Description</span></span>

<span data-ttu-id="ccc51-107">在状态 $ \ket{f_1} $ 和 $ \ket{f_2} $ 中分别给定了两个定点寄存器，执行操作 $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $。</span><span class="sxs-lookup"><span data-stu-id="ccc51-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="ccc51-108">输入</span><span class="sxs-lookup"><span data-stu-id="ccc51-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="ccc51-109">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ccc51-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ccc51-110">第一个固定点数字</span><span class="sxs-lookup"><span data-stu-id="ccc51-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="ccc51-111">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ccc51-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ccc51-112">第二个定点数将被更新，以包含两个输入的和。</span><span class="sxs-lookup"><span data-stu-id="ccc51-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ccc51-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccc51-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ccc51-114">注解</span><span class="sxs-lookup"><span data-stu-id="ccc51-114">Remarks</span></span>

<span data-ttu-id="ccc51-115">当前实现要求两个固定点数字与最小有效位之间具有相同的点位置计数，即 $n _i $，$p _i $ 必须相等。</span><span class="sxs-lookup"><span data-stu-id="ccc51-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>