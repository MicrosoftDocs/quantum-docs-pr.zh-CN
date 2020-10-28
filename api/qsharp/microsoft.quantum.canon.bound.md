---
uid: Microsoft.Quantum.Canon.Bound
title: 绑定函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696130"
---
# <a name="bound-function"></a><span data-ttu-id="c6a4f-102">绑定函数</span><span class="sxs-lookup"><span data-stu-id="c6a4f-102">Bound function</span></span>

<span data-ttu-id="c6a4f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6a4f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6a4f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6a4f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6a4f-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="c6a4f-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="c6a4f-106">输入</span><span class="sxs-lookup"><span data-stu-id="c6a4f-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="c6a4f-107">操作：不 => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="c6a4f-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="c6a4f-108">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="c6a4f-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="c6a4f-109">输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6a4f-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c6a4f-110">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="c6a4f-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c6a4f-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="c6a4f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c6a4f-112">找</span><span class="sxs-lookup"><span data-stu-id="c6a4f-112">'T</span></span>

<span data-ttu-id="c6a4f-113">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="c6a4f-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6a4f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a4f-114">See Also</span></span>

- [<span data-ttu-id="c6a4f-115">Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="c6a4f-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="c6a4f-116">Canon. BoundA</span><span class="sxs-lookup"><span data-stu-id="c6a4f-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="c6a4f-117">Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="c6a4f-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)