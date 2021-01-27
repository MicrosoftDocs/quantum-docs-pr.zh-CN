---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846685"
---
# <a name="dividei-operation"></a><span data-ttu-id="4c290-102">DivideI 操作</span><span class="sxs-lookup"><span data-stu-id="4c290-102">DivideI operation</span></span>

<span data-ttu-id="4c290-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4c290-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4c290-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4c290-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4c290-105">两个量程整数相除。</span><span class="sxs-lookup"><span data-stu-id="4c290-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4c290-106">说明</span><span class="sxs-lookup"><span data-stu-id="4c290-106">Description</span></span>

<span data-ttu-id="4c290-107">`xs` 将保留余数 `xs - floor(xs/ys) * ys` 并 `result` 保留 `floor(xs/ys)` 。</span><span class="sxs-lookup"><span data-stu-id="4c290-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="4c290-108">输入</span><span class="sxs-lookup"><span data-stu-id="4c290-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4c290-109">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4c290-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4c290-110">被除数 $n，将替换为余数。</span><span class="sxs-lookup"><span data-stu-id="4c290-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="4c290-111">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4c290-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4c290-112">$n $ 位除数</span><span class="sxs-lookup"><span data-stu-id="4c290-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="4c290-113">result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4c290-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4c290-114">$n $ 位结果，必须先处于状态 $ \ket {0} $，并将替换为整数相除的结果。</span><span class="sxs-lookup"><span data-stu-id="4c290-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c290-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c290-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4c290-116">备注</span><span class="sxs-lookup"><span data-stu-id="4c290-116">Remarks</span></span>

<span data-ttu-id="4c290-117">使用标准的移位和减法方法来实现除法。</span><span class="sxs-lookup"><span data-stu-id="4c290-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="4c290-118">受控版本是专用化的，因此不需要其他控制。</span><span class="sxs-lookup"><span data-stu-id="4c290-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>