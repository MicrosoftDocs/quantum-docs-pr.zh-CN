---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fa204433dc8195dd27fa40980fb2262f8a3848bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204838"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="47871-102">TransformedOperationCA 函数</span><span class="sxs-lookup"><span data-stu-id="47871-102">TransformedOperationCA function</span></span>

<span data-ttu-id="47871-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47871-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47871-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47871-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47871-105">给定一个函数和一个操作，返回一个新的操作，其输入由给定函数转换。</span><span class="sxs-lookup"><span data-stu-id="47871-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="47871-106">输入</span><span class="sxs-lookup"><span data-stu-id="47871-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="47871-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="47871-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="47871-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="47871-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="47871-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="47871-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="47871-110">要转换的操作。</span><span class="sxs-lookup"><span data-stu-id="47871-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj--ctl"></a><span data-ttu-id="47871-111">输出： "U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="47871-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="47871-112">新操作 tbat 的 `fn` 输入调用，然后将结果输出传递给 `op` 。</span><span class="sxs-lookup"><span data-stu-id="47871-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="47871-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="47871-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47871-114">找</span><span class="sxs-lookup"><span data-stu-id="47871-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="47871-115">' U</span><span class="sxs-lookup"><span data-stu-id="47871-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="47871-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47871-116">See Also</span></span>

- [<span data-ttu-id="47871-117">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="47871-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="47871-118">Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="47871-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="47871-119">Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="47871-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="47871-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="47871-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="47871-121">Canon。</span><span class="sxs-lookup"><span data-stu-id="47871-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)