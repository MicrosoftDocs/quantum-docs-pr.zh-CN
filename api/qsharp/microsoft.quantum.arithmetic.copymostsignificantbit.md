---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223283"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="ae332-102">CopyMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="ae332-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="ae332-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ae332-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ae332-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae332-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae332-105">将表示无符号整数的 qubit 寄存器的最高有效位复制 `from` 到 qubit 中 `target` 。</span><span class="sxs-lookup"><span data-stu-id="ae332-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ae332-106">输入</span><span class="sxs-lookup"><span data-stu-id="ae332-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="ae332-107">源： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ae332-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ae332-108">从中复制高位的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="ae332-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="ae332-109">此整数用小字节序格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="ae332-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ae332-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae332-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae332-111">要复制其最大位的 qubit。</span><span class="sxs-lookup"><span data-stu-id="ae332-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="ae332-112">位编码为计算基础。</span><span class="sxs-lookup"><span data-stu-id="ae332-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae332-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae332-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ae332-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae332-114">See Also</span></span>

- [<span data-ttu-id="ae332-115">LittleEndian。</span><span class="sxs-lookup"><span data-stu-id="ae332-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)