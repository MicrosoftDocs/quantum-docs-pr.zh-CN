---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696607"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="60e64-102">MultiplyFxP 操作</span><span class="sxs-lookup"><span data-stu-id="60e64-102">MultiplyFxP operation</span></span>

<span data-ttu-id="60e64-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="60e64-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="60e64-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60e64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60e64-105">将量程寄存器中的两个定点数相乘。</span><span class="sxs-lookup"><span data-stu-id="60e64-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="60e64-106">输入</span><span class="sxs-lookup"><span data-stu-id="60e64-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="60e64-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="60e64-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="60e64-108">第一个固定点号。</span><span class="sxs-lookup"><span data-stu-id="60e64-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="60e64-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="60e64-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="60e64-110">第二个定点数。</span><span class="sxs-lookup"><span data-stu-id="60e64-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="60e64-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="60e64-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="60e64-112">结果固定点数字，最初必须处于状态 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="60e64-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60e64-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60e64-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="60e64-114">注解</span><span class="sxs-lookup"><span data-stu-id="60e64-114">Remarks</span></span>

<span data-ttu-id="60e64-115">当前实现要求三个固定点数字具有相同的点位置和相同数量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="60e64-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>