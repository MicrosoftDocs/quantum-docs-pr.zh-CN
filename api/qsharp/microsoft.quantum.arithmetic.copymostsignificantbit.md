---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699897"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="cdd17-102">CopyMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="cdd17-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="cdd17-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cdd17-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cdd17-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cdd17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cdd17-105">将表示无符号整数的 qubit 寄存器的最高有效位复制 `from` 到 qubit 中 `target` 。</span><span class="sxs-lookup"><span data-stu-id="cdd17-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="cdd17-106">输入</span><span class="sxs-lookup"><span data-stu-id="cdd17-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="cdd17-107">源： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cdd17-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cdd17-108">从中复制高位的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="cdd17-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="cdd17-109">此整数用小字节序格式进行编码。</span><span class="sxs-lookup"><span data-stu-id="cdd17-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cdd17-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cdd17-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cdd17-111">要复制其最大位的 qubit。</span><span class="sxs-lookup"><span data-stu-id="cdd17-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="cdd17-112">位编码为计算基础。</span><span class="sxs-lookup"><span data-stu-id="cdd17-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdd17-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdd17-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="cdd17-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdd17-114">See Also</span></span>

- [<span data-ttu-id="cdd17-115">LittleEndian。</span><span class="sxs-lookup"><span data-stu-id="cdd17-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)