---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: ApplyReversedOpBECA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 5c761fb8e1042a25cd2e88f1b33e597c7d9287f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202713"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="1c2dd-102">ApplyReversedOpBECA 操作</span><span class="sxs-lookup"><span data-stu-id="1c2dd-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="1c2dd-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1c2dd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1c2dd-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c2dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c2dd-105">使用小 endian 格式将使用大字节序输入的操作应用到寄存器编码的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="1c2dd-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1c2dd-106">输入</span><span class="sxs-lookup"><span data-stu-id="1c2dd-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="1c2dd-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1c2dd-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1c2dd-108">作用于大字节序注册的操作。</span><span class="sxs-lookup"><span data-stu-id="1c2dd-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="1c2dd-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1c2dd-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1c2dd-110">要转换的小 endian 寄存器。</span><span class="sxs-lookup"><span data-stu-id="1c2dd-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c2dd-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c2dd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="1c2dd-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2dd-112">See Also</span></span>

- [<span data-ttu-id="1c2dd-113">ApplyReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="1c2dd-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="1c2dd-114">ApplyReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="1c2dd-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="1c2dd-115">ApplyReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="1c2dd-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)