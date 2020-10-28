---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696585"
---
# <a name="reversedople-function"></a><span data-ttu-id="f6ce1-102">ReversedOpLE 函数</span><span class="sxs-lookup"><span data-stu-id="f6ce1-102">ReversedOpLE function</span></span>

<span data-ttu-id="f6ce1-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f6ce1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f6ce1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6ce1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6ce1-105">给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="f6ce1-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="f6ce1-106">输入</span><span class="sxs-lookup"><span data-stu-id="f6ce1-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="f6ce1-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6ce1-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f6ce1-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="f6ce1-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="f6ce1-109">输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6ce1-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f6ce1-110">接受其输入作为大字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="f6ce1-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6ce1-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6ce1-111">See Also</span></span>

- [<span data-ttu-id="f6ce1-112">ApplyReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="f6ce1-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="f6ce1-113">ReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="f6ce1-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="f6ce1-114">ReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="f6ce1-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="f6ce1-115">ReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="f6ce1-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)