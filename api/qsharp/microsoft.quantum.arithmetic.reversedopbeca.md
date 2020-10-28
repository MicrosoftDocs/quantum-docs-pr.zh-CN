---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5617e191260903ac25effc8b922810932b7dc505
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696588"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="b6c39-102">ReversedOpBECA 函数</span><span class="sxs-lookup"><span data-stu-id="b6c39-102">ReversedOpBECA function</span></span>

<span data-ttu-id="b6c39-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b6c39-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b6c39-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6c39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6c39-105">给定一个采用大字节序输入的操作，将返回采用小 endian 输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="b6c39-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b6c39-106">输入</span><span class="sxs-lookup"><span data-stu-id="b6c39-106">Input</span></span>

### <a name="op--bigendian--unit-adj--ctl"></a><span data-ttu-id="b6c39-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b6c39-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b6c39-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="b6c39-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="b6c39-109">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b6c39-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b6c39-110">接受其输入作为小字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="b6c39-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6c39-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6c39-111">See Also</span></span>

- [<span data-ttu-id="b6c39-112">ApplyReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="b6c39-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="b6c39-113">ReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="b6c39-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="b6c39-114">ReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="b6c39-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="b6c39-115">ReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="b6c39-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)