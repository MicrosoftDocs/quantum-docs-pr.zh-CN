---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: MultiplySI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696602"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="ea9ce-102">MultiplySI 操作</span><span class="sxs-lookup"><span data-stu-id="ea9ce-102">MultiplySI operation</span></span>

<span data-ttu-id="ea9ce-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ea9ce-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ea9ce-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea9ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea9ce-105">将带符号整数与有符号整数相乘 `xs` `ys` 并将结果存储在中 `result` ，后者最初必须为零。</span><span class="sxs-lookup"><span data-stu-id="ea9ce-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ea9ce-106">输入</span><span class="sxs-lookup"><span data-stu-id="ea9ce-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="ea9ce-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea9ce-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="ea9ce-108">n 位被乘数 (SignedLittleEndian) </span><span class="sxs-lookup"><span data-stu-id="ea9ce-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="ea9ce-109">y) ： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea9ce-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="ea9ce-110">n 位乘法器 (SignedLittleEndian) </span><span class="sxs-lookup"><span data-stu-id="ea9ce-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="ea9ce-111">result： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea9ce-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="ea9ce-112"> (SignedLittleEndian) 的2n 位结果必须处于 $ \ket {0} $ 起初状态。</span><span class="sxs-lookup"><span data-stu-id="ea9ce-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea9ce-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea9ce-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

