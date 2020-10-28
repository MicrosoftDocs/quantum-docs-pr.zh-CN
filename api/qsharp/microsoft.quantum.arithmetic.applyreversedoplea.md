---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: ApplyReversedOpLEA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 073ba908f2a06d36a8b73237f6a12d974b9d4d15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699977"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="a753d-102">ApplyReversedOpLEA 操作</span><span class="sxs-lookup"><span data-stu-id="a753d-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="a753d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a753d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a753d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a753d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a753d-105">应用一个操作，该操作将使用大字节序格式对无符号整数进行寄存器编码。</span><span class="sxs-lookup"><span data-stu-id="a753d-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a753d-106">输入</span><span class="sxs-lookup"><span data-stu-id="a753d-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="a753d-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="a753d-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a753d-108">作用于小 endian 寄存器的操作。</span><span class="sxs-lookup"><span data-stu-id="a753d-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="a753d-109">register： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="a753d-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="a753d-110">要转换的大字节序寄存器。</span><span class="sxs-lookup"><span data-stu-id="a753d-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a753d-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a753d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a753d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a753d-112">See Also</span></span>

- [<span data-ttu-id="a753d-113">ApplyReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="a753d-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="a753d-114">ApplyReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="a753d-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="a753d-115">ApplyReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="a753d-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)