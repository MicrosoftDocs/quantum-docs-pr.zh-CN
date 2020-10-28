---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 3a4872be6b81498c26ab9a14134940c5ef8628b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696583"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="0c5ac-102">ReversedOpLEC 函数</span><span class="sxs-lookup"><span data-stu-id="0c5ac-102">ReversedOpLEC function</span></span>

<span data-ttu-id="0c5ac-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0c5ac-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0c5ac-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c5ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c5ac-105">给定一个采用小 endian 输入的操作，将返回采用大字节序输入的新操作。</span><span class="sxs-lookup"><span data-stu-id="0c5ac-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0c5ac-106">输入</span><span class="sxs-lookup"><span data-stu-id="0c5ac-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="0c5ac-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="0c5ac-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0c5ac-108">要反转其输入的操作。</span><span class="sxs-lookup"><span data-stu-id="0c5ac-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-ctl"></a><span data-ttu-id="0c5ac-109">输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="0c5ac-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0c5ac-110">接受其输入作为大字节序注册的新操作。</span><span class="sxs-lookup"><span data-stu-id="0c5ac-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c5ac-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c5ac-111">See Also</span></span>

- [<span data-ttu-id="0c5ac-112">ApplyReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="0c5ac-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="0c5ac-113">ReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="0c5ac-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="0c5ac-114">ReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="0c5ac-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="0c5ac-115">ReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="0c5ac-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)