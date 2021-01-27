---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: e9c245fb7c0cf3a6b1b98eb01cd582c325917602
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843301"
---
# <a name="comparegti-operation"></a><span data-ttu-id="e303c-102">CompareGTI 操作</span><span class="sxs-lookup"><span data-stu-id="e303c-102">CompareGTI operation</span></span>

<span data-ttu-id="e303c-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e303c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e303c-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="e303c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="e303c-105">整数比较的包装器： `result = x > y` 。</span><span class="sxs-lookup"><span data-stu-id="e303c-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e303c-106">输入</span><span class="sxs-lookup"><span data-stu-id="e303c-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e303c-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e303c-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e303c-108">第一个 $n $ 位数字</span><span class="sxs-lookup"><span data-stu-id="e303c-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e303c-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e303c-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e303c-110">第二 $n $ 位数字</span><span class="sxs-lookup"><span data-stu-id="e303c-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="e303c-111">result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e303c-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e303c-112">如果 $x > y $，将翻转</span><span class="sxs-lookup"><span data-stu-id="e303c-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="e303c-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e303c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

