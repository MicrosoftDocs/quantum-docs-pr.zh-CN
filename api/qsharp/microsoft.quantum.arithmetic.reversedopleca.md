---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b5413e43ad50ba7252705ef53b21e63650dbb2a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696580"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="b7534-102">ReversedOpLECA 函数</span><span class="sxs-lookup"><span data-stu-id="b7534-102">ReversedOpLECA function</span></span>

<span data-ttu-id="b7534-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b7534-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b7534-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7534-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7534-105">给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="b7534-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b7534-106">输入</span><span class="sxs-lookup"><span data-stu-id="b7534-106">Input</span></span>

### <a name="op--littleendian--unit-adj--ctl"></a><span data-ttu-id="b7534-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b7534-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b7534-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="b7534-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj--ctl"></a><span data-ttu-id="b7534-109">输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b7534-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b7534-110">接受其输入作为大字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="b7534-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7534-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7534-111">See Also</span></span>

- [<span data-ttu-id="b7534-112">ApplyReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="b7534-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="b7534-113">ReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="b7534-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="b7534-114">ReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="b7534-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="b7534-115">ReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="b7534-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)