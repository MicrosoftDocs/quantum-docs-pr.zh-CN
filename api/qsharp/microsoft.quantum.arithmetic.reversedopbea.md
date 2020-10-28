---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696593"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="58fbc-102">ReversedOpBEA 函数</span><span class="sxs-lookup"><span data-stu-id="58fbc-102">ReversedOpBEA function</span></span>

<span data-ttu-id="58fbc-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="58fbc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="58fbc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58fbc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58fbc-105">给定一个采用大字节序输入的操作，将返回采用小 endian 输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="58fbc-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="58fbc-106">输入</span><span class="sxs-lookup"><span data-stu-id="58fbc-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="58fbc-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="58fbc-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="58fbc-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="58fbc-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj"></a><span data-ttu-id="58fbc-109">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="58fbc-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="58fbc-110">接受其输入作为小字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="58fbc-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="58fbc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58fbc-111">See Also</span></span>

- [<span data-ttu-id="58fbc-112">ApplyReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="58fbc-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="58fbc-113">ReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="58fbc-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="58fbc-114">ReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="58fbc-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="58fbc-115">ReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="58fbc-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)