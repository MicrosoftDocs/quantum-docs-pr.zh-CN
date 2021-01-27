---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843852"
---
# <a name="addi-operation"></a><span data-ttu-id="502a3-102">AddI 操作</span><span class="sxs-lookup"><span data-stu-id="502a3-102">AddI operation</span></span>

<span data-ttu-id="502a3-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="502a3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="502a3-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="502a3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="502a3-105">根据的寄存器大小，自动选择 "执行" 和 "无" `ys` 。</span><span class="sxs-lookup"><span data-stu-id="502a3-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="502a3-106">输入</span><span class="sxs-lookup"><span data-stu-id="502a3-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="502a3-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="502a3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="502a3-108">$n $ 加数。</span><span class="sxs-lookup"><span data-stu-id="502a3-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="502a3-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="502a3-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="502a3-110">至少 $n $ qubits 的加数。</span><span class="sxs-lookup"><span data-stu-id="502a3-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="502a3-111">将保存结果。</span><span class="sxs-lookup"><span data-stu-id="502a3-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="502a3-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="502a3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

