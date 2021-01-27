---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 878b0fae8a803b3136d1537309c945c052e1052c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846485"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="d87ad-102">ReversedOpBE 函数</span><span class="sxs-lookup"><span data-stu-id="d87ad-102">ReversedOpBE function</span></span>

<span data-ttu-id="d87ad-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d87ad-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d87ad-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d87ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d87ad-105">给定一个采用大字节序输入的操作，将返回采用小 endian 输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="d87ad-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="d87ad-106">输入</span><span class="sxs-lookup"><span data-stu-id="d87ad-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="d87ad-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d87ad-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d87ad-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="d87ad-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="d87ad-109">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d87ad-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d87ad-110">接受其输入作为小字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="d87ad-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="d87ad-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d87ad-111">See Also</span></span>

- [<span data-ttu-id="d87ad-112">ApplyReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="d87ad-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="d87ad-113">ReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="d87ad-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="d87ad-114">ReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="d87ad-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="d87ad-115">ReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="d87ad-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)