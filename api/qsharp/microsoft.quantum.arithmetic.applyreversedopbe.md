---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: a181cb16d6ae7684d49fe200d72bcbf5209018e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699997"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="0f5dd-102">ApplyReversedOpBE 操作</span><span class="sxs-lookup"><span data-stu-id="0f5dd-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="0f5dd-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0f5dd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0f5dd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f5dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f5dd-105">使用小 endian 格式将使用大字节序输入的操作应用到寄存器编码的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="0f5dd-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="0f5dd-106">输入</span><span class="sxs-lookup"><span data-stu-id="0f5dd-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="0f5dd-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f5dd-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0f5dd-108">作用于大字节序注册的操作。</span><span class="sxs-lookup"><span data-stu-id="0f5dd-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="0f5dd-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f5dd-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f5dd-110">要转换的小 endian 寄存器。</span><span class="sxs-lookup"><span data-stu-id="0f5dd-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f5dd-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f5dd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0f5dd-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f5dd-112">See Also</span></span>

- [<span data-ttu-id="0f5dd-113">ApplyReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="0f5dd-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="0f5dd-114">ApplyReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="0f5dd-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="0f5dd-115">ApplyReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="0f5dd-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)