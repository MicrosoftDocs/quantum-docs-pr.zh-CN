---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842925"
---
# <a name="squaresi-operation"></a><span data-ttu-id="008f3-102">SquareSI 操作</span><span class="sxs-lookup"><span data-stu-id="008f3-102">SquareSI operation</span></span>

<span data-ttu-id="008f3-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="008f3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="008f3-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="008f3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="008f3-105">方形有符号整数， `xs` 并将结果存储在中 `result` ，后者最初必须为零。</span><span class="sxs-lookup"><span data-stu-id="008f3-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="008f3-106">输入</span><span class="sxs-lookup"><span data-stu-id="008f3-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="008f3-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="008f3-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="008f3-108">n 位整数到平方 (SignedLittleEndian) </span><span class="sxs-lookup"><span data-stu-id="008f3-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="008f3-109">result： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="008f3-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="008f3-110"> (SignedLittleEndian) 的2n 位结果必须处于 $ \ket {0} $ 起初状态。</span><span class="sxs-lookup"><span data-stu-id="008f3-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="008f3-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="008f3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="008f3-112">备注</span><span class="sxs-lookup"><span data-stu-id="008f3-112">Remarks</span></span>

<span data-ttu-id="008f3-113">实现依赖于 IntegerSquare。</span><span class="sxs-lookup"><span data-stu-id="008f3-113">The implementation relies on IntegerSquare.</span></span>