---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191017"
---
# <a name="addi-operation"></a><span data-ttu-id="81b2d-102">AddI 操作</span><span class="sxs-lookup"><span data-stu-id="81b2d-102">AddI operation</span></span>

<span data-ttu-id="81b2d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="81b2d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="81b2d-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="81b2d-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="81b2d-105">根据的寄存器大小，自动选择 "执行" 和 "无" `ys` 。</span><span class="sxs-lookup"><span data-stu-id="81b2d-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="81b2d-106">输入</span><span class="sxs-lookup"><span data-stu-id="81b2d-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="81b2d-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81b2d-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81b2d-108">$n $ 加数。</span><span class="sxs-lookup"><span data-stu-id="81b2d-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="81b2d-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81b2d-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81b2d-110">至少 $n $ qubits 的加数。</span><span class="sxs-lookup"><span data-stu-id="81b2d-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="81b2d-111">将保存结果。</span><span class="sxs-lookup"><span data-stu-id="81b2d-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81b2d-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81b2d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

