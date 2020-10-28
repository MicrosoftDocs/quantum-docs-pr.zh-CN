---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696584"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="2ba2f-102">ReversedOpLEA 函数</span><span class="sxs-lookup"><span data-stu-id="2ba2f-102">ReversedOpLEA function</span></span>

<span data-ttu-id="2ba2f-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2ba2f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2ba2f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ba2f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ba2f-105">给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="2ba2f-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="2ba2f-106">输入</span><span class="sxs-lookup"><span data-stu-id="2ba2f-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="2ba2f-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="2ba2f-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2ba2f-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="2ba2f-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj"></a><span data-ttu-id="2ba2f-109">输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="2ba2f-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2ba2f-110">接受其输入作为大字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="2ba2f-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ba2f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ba2f-111">See Also</span></span>

- [<span data-ttu-id="2ba2f-112">ApplyReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="2ba2f-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="2ba2f-113">ReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="2ba2f-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="2ba2f-114">ReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="2ba2f-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="2ba2f-115">ReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="2ba2f-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)