---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: ApplyReversedOpLE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 16ce6842cdef8e519a13a45640edc3d79cdbce25
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202747"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="6cb25-102">ApplyReversedOpLE 操作</span><span class="sxs-lookup"><span data-stu-id="6cb25-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="6cb25-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6cb25-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6cb25-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6cb25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6cb25-105">应用一个操作，该操作将使用大字节序格式对无符号整数进行寄存器编码。</span><span class="sxs-lookup"><span data-stu-id="6cb25-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6cb25-106">输入</span><span class="sxs-lookup"><span data-stu-id="6cb25-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="6cb25-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cb25-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6cb25-108">作用于小 endian 寄存器的操作。</span><span class="sxs-lookup"><span data-stu-id="6cb25-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="6cb25-109">register： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="6cb25-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="6cb25-110">要转换的大字节序寄存器。</span><span class="sxs-lookup"><span data-stu-id="6cb25-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6cb25-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cb25-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6cb25-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cb25-112">See Also</span></span>

- [<span data-ttu-id="6cb25-113">ApplyReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="6cb25-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="6cb25-114">ApplyReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="6cb25-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="6cb25-115">ApplyReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="6cb25-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)