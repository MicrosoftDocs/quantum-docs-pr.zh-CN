---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844542"
---
# <a name="bounda-function"></a><span data-ttu-id="b91fb-102">BoundA 函数</span><span class="sxs-lookup"><span data-stu-id="b91fb-102">BoundA function</span></span>

<span data-ttu-id="b91fb-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b91fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b91fb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b91fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b91fb-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="b91fb-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="b91fb-106">修饰符 `A` 指示数组中的所有操作都是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="b91fb-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="b91fb-107">输入</span><span class="sxs-lookup"><span data-stu-id="b91fb-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="b91fb-108">操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 []</span><span class="sxs-lookup"><span data-stu-id="b91fb-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="b91fb-109">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="b91fb-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="b91fb-110">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="b91fb-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b91fb-111">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="b91fb-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b91fb-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="b91fb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b91fb-113">找</span><span class="sxs-lookup"><span data-stu-id="b91fb-113">'T</span></span>

<span data-ttu-id="b91fb-114">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="b91fb-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="b91fb-115">示例</span><span class="sxs-lookup"><span data-stu-id="b91fb-115">Example</span></span>

<span data-ttu-id="b91fb-116">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="b91fb-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="b91fb-117">和</span><span class="sxs-lookup"><span data-stu-id="b91fb-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="b91fb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b91fb-118">See Also</span></span>

- [<span data-ttu-id="b91fb-119">Canon。</span><span class="sxs-lookup"><span data-stu-id="b91fb-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)