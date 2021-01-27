---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d02817e5372b841f3ab633cafa22af603c5310c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846396"
---
# <a name="reversedople-function"></a><span data-ttu-id="aa3be-102">ReversedOpLE 函数</span><span class="sxs-lookup"><span data-stu-id="aa3be-102">ReversedOpLE function</span></span>

<span data-ttu-id="aa3be-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aa3be-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aa3be-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa3be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa3be-105">给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="aa3be-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="aa3be-106">输入</span><span class="sxs-lookup"><span data-stu-id="aa3be-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="aa3be-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa3be-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="aa3be-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="aa3be-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="aa3be-109">输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa3be-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="aa3be-110">接受其输入作为大字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="aa3be-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa3be-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa3be-111">See Also</span></span>

- [<span data-ttu-id="aa3be-112">ApplyReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="aa3be-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="aa3be-113">ReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="aa3be-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="aa3be-114">ReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="aa3be-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="aa3be-115">ReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="aa3be-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)