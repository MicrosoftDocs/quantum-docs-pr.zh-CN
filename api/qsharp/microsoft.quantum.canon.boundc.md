---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207575"
---
# <a name="boundc-function"></a><span data-ttu-id="69c7a-102">BoundC 函数</span><span class="sxs-lookup"><span data-stu-id="69c7a-102">BoundC function</span></span>

<span data-ttu-id="69c7a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69c7a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69c7a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69c7a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69c7a-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="69c7a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="69c7a-106">修饰符 `C` 指示数组中的所有操作都可控制。</span><span class="sxs-lookup"><span data-stu-id="69c7a-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="69c7a-107">输入</span><span class="sxs-lookup"><span data-stu-id="69c7a-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="69c7a-108">操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl []</span><span class="sxs-lookup"><span data-stu-id="69c7a-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="69c7a-109">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="69c7a-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="69c7a-110">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="69c7a-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="69c7a-111">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="69c7a-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="69c7a-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="69c7a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69c7a-113">找</span><span class="sxs-lookup"><span data-stu-id="69c7a-113">'T</span></span>

<span data-ttu-id="69c7a-114">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="69c7a-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="69c7a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69c7a-115">See Also</span></span>

- [<span data-ttu-id="69c7a-116">Canon。</span><span class="sxs-lookup"><span data-stu-id="69c7a-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)