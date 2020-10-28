---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695935"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="5bdff-102">TransformedOperation 函数</span><span class="sxs-lookup"><span data-stu-id="5bdff-102">TransformedOperation function</span></span>

<span data-ttu-id="5bdff-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5bdff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5bdff-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5bdff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5bdff-105">给定一个函数和一个操作，返回一个新的操作，其输入由给定函数转换。</span><span class="sxs-lookup"><span data-stu-id="5bdff-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="5bdff-106">输入</span><span class="sxs-lookup"><span data-stu-id="5bdff-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="5bdff-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="5bdff-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="5bdff-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="5bdff-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="5bdff-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bdff-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5bdff-110">要转换的操作。</span><span class="sxs-lookup"><span data-stu-id="5bdff-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="5bdff-111">输出： "U => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bdff-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5bdff-112">新操作 tbat 的 `fn` 输入调用，然后将结果输出传递给 `op` 。</span><span class="sxs-lookup"><span data-stu-id="5bdff-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5bdff-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="5bdff-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5bdff-114">找</span><span class="sxs-lookup"><span data-stu-id="5bdff-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5bdff-115">' U</span><span class="sxs-lookup"><span data-stu-id="5bdff-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="5bdff-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bdff-116">See Also</span></span>

- [<span data-ttu-id="5bdff-117">Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="5bdff-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="5bdff-118">Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="5bdff-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="5bdff-119">Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="5bdff-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="5bdff-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="5bdff-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="5bdff-121">Canon。</span><span class="sxs-lookup"><span data-stu-id="5bdff-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)