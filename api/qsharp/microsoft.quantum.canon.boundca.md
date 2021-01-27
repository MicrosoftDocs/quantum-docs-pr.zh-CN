---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844530"
---
# <a name="boundca-function"></a><span data-ttu-id="203bd-102">BoundCA 函数</span><span class="sxs-lookup"><span data-stu-id="203bd-102">BoundCA function</span></span>

<span data-ttu-id="203bd-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="203bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="203bd-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="203bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="203bd-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="203bd-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="203bd-106">修饰符 `CA` 指示数组中的所有操作都是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="203bd-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="203bd-107">输入</span><span class="sxs-lookup"><span data-stu-id="203bd-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="203bd-108">操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为调整 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="203bd-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="203bd-109">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="203bd-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="203bd-110">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="203bd-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="203bd-111">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="203bd-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="203bd-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="203bd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="203bd-113">找</span><span class="sxs-lookup"><span data-stu-id="203bd-113">'T</span></span>

<span data-ttu-id="203bd-114">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="203bd-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="203bd-115">示例</span><span class="sxs-lookup"><span data-stu-id="203bd-115">Example</span></span>

<span data-ttu-id="203bd-116">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="203bd-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="203bd-117">和</span><span class="sxs-lookup"><span data-stu-id="203bd-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="203bd-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="203bd-118">See Also</span></span>

- [<span data-ttu-id="203bd-119">Canon。</span><span class="sxs-lookup"><span data-stu-id="203bd-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)