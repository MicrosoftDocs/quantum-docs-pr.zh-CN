---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696120"
---
# <a name="boundca-function"></a><span data-ttu-id="baadd-102">BoundCA 函数</span><span class="sxs-lookup"><span data-stu-id="baadd-102">BoundCA function</span></span>

<span data-ttu-id="baadd-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="baadd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="baadd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="baadd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="baadd-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="baadd-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="baadd-106">修饰符 `CA` 指示数组中的所有操作都是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="baadd-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="baadd-107">输入</span><span class="sxs-lookup"><span data-stu-id="baadd-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="baadd-108">操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="baadd-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="baadd-109">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="baadd-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="baadd-110">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="baadd-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="baadd-111">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="baadd-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="baadd-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="baadd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="baadd-113">找</span><span class="sxs-lookup"><span data-stu-id="baadd-113">'T</span></span>

<span data-ttu-id="baadd-114">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="baadd-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="baadd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="baadd-115">See Also</span></span>

- [<span data-ttu-id="baadd-116">Canon。</span><span class="sxs-lookup"><span data-stu-id="baadd-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)