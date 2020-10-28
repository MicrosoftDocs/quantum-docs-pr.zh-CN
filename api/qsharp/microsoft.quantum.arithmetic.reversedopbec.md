---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696590"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="b621e-102">ReversedOpBEC 函数</span><span class="sxs-lookup"><span data-stu-id="b621e-102">ReversedOpBEC function</span></span>

<span data-ttu-id="b621e-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b621e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b621e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b621e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b621e-105">给定一个采用大字节序输入的操作，将返回采用小 endian 输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="b621e-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="b621e-106">输入</span><span class="sxs-lookup"><span data-stu-id="b621e-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="b621e-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="b621e-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b621e-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="b621e-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-ctl"></a><span data-ttu-id="b621e-109">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="b621e-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b621e-110">接受其输入作为小字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="b621e-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="b621e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b621e-111">See Also</span></span>

- [<span data-ttu-id="b621e-112">ApplyReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="b621e-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="b621e-113">ReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="b621e-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="b621e-114">ReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="b621e-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="b621e-115">ReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="b621e-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)