---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 170f63e60e6c26dbdd33af02c6a3387a1b3dbc44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696594"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="69a5c-102">ReversedOpBE 函数</span><span class="sxs-lookup"><span data-stu-id="69a5c-102">ReversedOpBE function</span></span>

<span data-ttu-id="69a5c-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="69a5c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="69a5c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69a5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69a5c-105">给定一个采用大字节序输入的操作，将返回采用小 endian 输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="69a5c-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="69a5c-106">输入</span><span class="sxs-lookup"><span data-stu-id="69a5c-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="69a5c-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69a5c-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="69a5c-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="69a5c-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="69a5c-109">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69a5c-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="69a5c-110">接受其输入作为小字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="69a5c-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="69a5c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69a5c-111">See Also</span></span>

- [<span data-ttu-id="69a5c-112">ApplyReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="69a5c-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="69a5c-113">ReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="69a5c-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="69a5c-114">ReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="69a5c-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="69a5c-115">ReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="69a5c-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)