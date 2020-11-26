---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223300"
---
# <a name="dividei-operation"></a><span data-ttu-id="d9fd4-102">DivideI 操作</span><span class="sxs-lookup"><span data-stu-id="d9fd4-102">DivideI operation</span></span>

<span data-ttu-id="d9fd4-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d9fd4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d9fd4-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d9fd4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d9fd4-105">两个量程整数相除。</span><span class="sxs-lookup"><span data-stu-id="d9fd4-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d9fd4-106">描述</span><span class="sxs-lookup"><span data-stu-id="d9fd4-106">Description</span></span>

<span data-ttu-id="d9fd4-107">`xs` 将保留余数 `xs - floor(xs/ys) * ys` 并 `result` 保留 `floor(xs/ys)` 。</span><span class="sxs-lookup"><span data-stu-id="d9fd4-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="d9fd4-108">输入</span><span class="sxs-lookup"><span data-stu-id="d9fd4-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d9fd4-109">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d9fd4-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d9fd4-110">被除数 $n，将替换为余数。</span><span class="sxs-lookup"><span data-stu-id="d9fd4-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d9fd4-111">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d9fd4-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d9fd4-112">$n $ 位除数</span><span class="sxs-lookup"><span data-stu-id="d9fd4-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="d9fd4-113">result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d9fd4-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d9fd4-114">$n $ 位结果，必须先处于状态 $ \ket {0} $，并将替换为整数相除的结果。</span><span class="sxs-lookup"><span data-stu-id="d9fd4-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9fd4-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9fd4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d9fd4-116">备注</span><span class="sxs-lookup"><span data-stu-id="d9fd4-116">Remarks</span></span>

<span data-ttu-id="d9fd4-117">使用标准的移位和减法方法来实现除法。</span><span class="sxs-lookup"><span data-stu-id="d9fd4-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="d9fd4-118">受控版本是专用化的，因此不需要其他控制。</span><span class="sxs-lookup"><span data-stu-id="d9fd4-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>