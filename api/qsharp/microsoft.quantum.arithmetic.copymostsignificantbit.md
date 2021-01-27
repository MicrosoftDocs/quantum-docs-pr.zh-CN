---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843270"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="b6e11-102">CopyMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="b6e11-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="b6e11-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b6e11-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b6e11-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6e11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6e11-105">将表示无符号整数的 qubit 寄存器的最高有效位复制 `from` 到 qubit 中 `target` 。</span><span class="sxs-lookup"><span data-stu-id="b6e11-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b6e11-106">输入</span><span class="sxs-lookup"><span data-stu-id="b6e11-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="b6e11-107">源： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b6e11-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b6e11-108">从中复制高位的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="b6e11-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="b6e11-109">此整数用小字节序格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="b6e11-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b6e11-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b6e11-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b6e11-111">要复制其最大位的 qubit。</span><span class="sxs-lookup"><span data-stu-id="b6e11-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="b6e11-112">位编码为计算基础。</span><span class="sxs-lookup"><span data-stu-id="b6e11-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6e11-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6e11-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b6e11-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6e11-114">See Also</span></span>

- [<span data-ttu-id="b6e11-115">LittleEndian。</span><span class="sxs-lookup"><span data-stu-id="b6e11-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)