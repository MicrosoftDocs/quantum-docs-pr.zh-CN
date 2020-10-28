---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699901"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="bb2ae-102">ComputeReciprocalI 操作</span><span class="sxs-lookup"><span data-stu-id="bb2ae-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="bb2ae-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bb2ae-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bb2ae-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb2ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb2ae-105">使用整除计算无符号整数 x 的倒数 1/x。</span><span class="sxs-lookup"><span data-stu-id="bb2ae-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="bb2ae-106">解释为整数的结果将为 `floor(2^(2*n-1) / x)` 。</span><span class="sxs-lookup"><span data-stu-id="bb2ae-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="bb2ae-107">输入</span><span class="sxs-lookup"><span data-stu-id="bb2ae-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="bb2ae-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bb2ae-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bb2ae-109">n 位无符号整数</span><span class="sxs-lookup"><span data-stu-id="bb2ae-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="bb2ae-110">result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bb2ae-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bb2ae-111">2n 位输出，最初必须为 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="bb2ae-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bb2ae-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb2ae-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bb2ae-113">注解</span><span class="sxs-lookup"><span data-stu-id="bb2ae-113">Remarks</span></span>

<span data-ttu-id="bb2ae-114">对于输入 x = 0，输出将为全部输出。</span><span class="sxs-lookup"><span data-stu-id="bb2ae-114">For the input x=0, the output will be all-ones.</span></span>