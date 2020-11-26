---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216874"
---
# <a name="boundca-function"></a><span data-ttu-id="ab492-102">BoundCA 函数</span><span class="sxs-lookup"><span data-stu-id="ab492-102">BoundCA function</span></span>

<span data-ttu-id="ab492-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab492-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab492-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab492-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab492-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="ab492-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="ab492-106">修饰符 `CA` 指示数组中的所有操作都是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="ab492-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ab492-107">输入</span><span class="sxs-lookup"><span data-stu-id="ab492-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="ab492-108">操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为调整 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="ab492-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="ab492-109">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="ab492-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="ab492-110">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ab492-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ab492-111">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="ab492-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ab492-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="ab492-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab492-113">找</span><span class="sxs-lookup"><span data-stu-id="ab492-113">'T</span></span>

<span data-ttu-id="ab492-114">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="ab492-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab492-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab492-115">See Also</span></span>

- [<span data-ttu-id="ab492-116">Canon。</span><span class="sxs-lookup"><span data-stu-id="ab492-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)