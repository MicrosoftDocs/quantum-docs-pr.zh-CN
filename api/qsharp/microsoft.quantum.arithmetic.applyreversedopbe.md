---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 6db1fcb7437d97b1e56c64165d1be523ed2df07a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202849"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="9d387-102">ApplyReversedOpBE 操作</span><span class="sxs-lookup"><span data-stu-id="9d387-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="9d387-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9d387-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9d387-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d387-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d387-105">使用小 endian 格式将使用大字节序输入的操作应用到寄存器编码的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="9d387-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="9d387-106">输入</span><span class="sxs-lookup"><span data-stu-id="9d387-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="9d387-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d387-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9d387-108">作用于大字节序注册的操作。</span><span class="sxs-lookup"><span data-stu-id="9d387-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="9d387-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9d387-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9d387-110">要转换的小 endian 寄存器。</span><span class="sxs-lookup"><span data-stu-id="9d387-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d387-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d387-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9d387-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d387-112">See Also</span></span>

- [<span data-ttu-id="9d387-113">ApplyReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="9d387-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="9d387-114">ApplyReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="9d387-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="9d387-115">ApplyReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="9d387-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)