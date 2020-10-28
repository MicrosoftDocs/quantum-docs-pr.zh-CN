---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696566"
---
# <a name="squaresi-operation"></a><span data-ttu-id="2be8d-102">SquareSI 操作</span><span class="sxs-lookup"><span data-stu-id="2be8d-102">SquareSI operation</span></span>

<span data-ttu-id="2be8d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2be8d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2be8d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2be8d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2be8d-105">方形有符号整数， `xs` 并将结果存储在中 `result` ，后者最初必须为零。</span><span class="sxs-lookup"><span data-stu-id="2be8d-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2be8d-106">输入</span><span class="sxs-lookup"><span data-stu-id="2be8d-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="2be8d-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2be8d-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="2be8d-108">n 位整数到平方 (SignedLittleEndian) </span><span class="sxs-lookup"><span data-stu-id="2be8d-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="2be8d-109">result： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2be8d-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="2be8d-110"> (SignedLittleEndian) 的2n 位结果必须处于 $ \ket {0} $ 起初状态。</span><span class="sxs-lookup"><span data-stu-id="2be8d-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2be8d-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2be8d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2be8d-112">注解</span><span class="sxs-lookup"><span data-stu-id="2be8d-112">Remarks</span></span>

<span data-ttu-id="2be8d-113">实现依赖于 IntegerSquare。</span><span class="sxs-lookup"><span data-stu-id="2be8d-113">The implementation relies on IntegerSquare.</span></span>