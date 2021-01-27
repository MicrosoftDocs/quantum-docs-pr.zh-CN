---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: f725bdbaa945a4f87e90fc71930c37642113c21a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846693"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="1e102-102">CompareGTSI 操作</span><span class="sxs-lookup"><span data-stu-id="1e102-102">CompareGTSI operation</span></span>

<span data-ttu-id="1e102-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1e102-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1e102-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="1e102-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="1e102-105">带符号整数比较的包装器： `result = xs > ys` 。</span><span class="sxs-lookup"><span data-stu-id="1e102-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1e102-106">输入</span><span class="sxs-lookup"><span data-stu-id="1e102-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="1e102-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1e102-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1e102-108">第一个 $n $ 位数字</span><span class="sxs-lookup"><span data-stu-id="1e102-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="1e102-109">y) ： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1e102-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1e102-110">第二 $n $ 位数字</span><span class="sxs-lookup"><span data-stu-id="1e102-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="1e102-111">result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1e102-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1e102-112">如果 $xs > y) $，将进行翻转</span><span class="sxs-lookup"><span data-stu-id="1e102-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e102-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e102-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

