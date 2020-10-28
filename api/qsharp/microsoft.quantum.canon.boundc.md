---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696125"
---
# <a name="boundc-function"></a><span data-ttu-id="602ad-102">BoundC 函数</span><span class="sxs-lookup"><span data-stu-id="602ad-102">BoundC function</span></span>

<span data-ttu-id="602ad-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="602ad-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="602ad-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="602ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="602ad-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="602ad-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="602ad-106">修饰符 `C` 指示数组中的所有操作都可控制。</span><span class="sxs-lookup"><span data-stu-id="602ad-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="602ad-107">输入</span><span class="sxs-lookup"><span data-stu-id="602ad-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="602ad-108">操作：不 => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl []</span><span class="sxs-lookup"><span data-stu-id="602ad-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="602ad-109">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="602ad-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="602ad-110">输出：不 => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="602ad-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="602ad-111">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="602ad-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="602ad-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="602ad-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="602ad-113">找</span><span class="sxs-lookup"><span data-stu-id="602ad-113">'T</span></span>

<span data-ttu-id="602ad-114">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="602ad-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="602ad-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="602ad-115">See Also</span></span>

- [<span data-ttu-id="602ad-116">Canon。</span><span class="sxs-lookup"><span data-stu-id="602ad-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)