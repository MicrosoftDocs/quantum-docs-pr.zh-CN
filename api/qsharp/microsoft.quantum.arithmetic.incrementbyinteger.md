---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843174"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="0802f-102">IncrementByInteger 操作</span><span class="sxs-lookup"><span data-stu-id="0802f-102">IncrementByInteger operation</span></span>

<span data-ttu-id="0802f-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0802f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0802f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0802f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0802f-105">使用阶段旋转，将未签名的量程寄存器增加一个传统整数。</span><span class="sxs-lookup"><span data-stu-id="0802f-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0802f-106">说明</span><span class="sxs-lookup"><span data-stu-id="0802f-106">Description</span></span>

<span data-ttu-id="0802f-107">假定将 `target` 无符号整数编码 $x $ in 小字节序编码，并且 `increment` 等于 $a $。</span><span class="sxs-lookup"><span data-stu-id="0802f-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="0802f-108">然后，此操作实现一个单一 $ \ket{x} \mapsto \ket{x + a} $，其中添加操作执行取模 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。</span><span class="sxs-lookup"><span data-stu-id="0802f-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="0802f-109">输入</span><span class="sxs-lookup"><span data-stu-id="0802f-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="0802f-110">增量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0802f-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0802f-111">的整数，该整数用于 `target` 递增。</span><span class="sxs-lookup"><span data-stu-id="0802f-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="0802f-112">目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0802f-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0802f-113">量程寄存器使用小字节序编码对无符号整数进行编码。</span><span class="sxs-lookup"><span data-stu-id="0802f-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0802f-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0802f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

