---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA
title: ApplyReversedOpLECA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLECA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: c0bc04efe55792f5e177266c27552fb0546707e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202577"
---
# <a name="applyreversedopleca-operation"></a><span data-ttu-id="3ed15-102">ApplyReversedOpLECA 操作</span><span class="sxs-lookup"><span data-stu-id="3ed15-102">ApplyReversedOpLECA operation</span></span>

<span data-ttu-id="3ed15-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3ed15-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3ed15-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ed15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ed15-105">应用一个操作，该操作将使用大字节序格式对无符号整数进行寄存器编码。</span><span class="sxs-lookup"><span data-stu-id="3ed15-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3ed15-106">输入</span><span class="sxs-lookup"><span data-stu-id="3ed15-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="3ed15-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="3ed15-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3ed15-108">作用于小 endian 寄存器的操作。</span><span class="sxs-lookup"><span data-stu-id="3ed15-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="3ed15-109">register： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="3ed15-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="3ed15-110">要转换的大字节序寄存器。</span><span class="sxs-lookup"><span data-stu-id="3ed15-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ed15-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ed15-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3ed15-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ed15-112">See Also</span></span>

- [<span data-ttu-id="3ed15-113">ApplyReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="3ed15-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="3ed15-114">ApplyReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="3ed15-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="3ed15-115">ApplyReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="3ed15-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)