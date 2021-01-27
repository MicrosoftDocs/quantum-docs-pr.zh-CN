---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852057"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="be4ca-102">TransformedOperation 函数</span><span class="sxs-lookup"><span data-stu-id="be4ca-102">TransformedOperation function</span></span>

<span data-ttu-id="be4ca-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be4ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be4ca-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be4ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be4ca-105">给定一个函数和一个操作，返回一个新的操作，其输入由给定函数转换。</span><span class="sxs-lookup"><span data-stu-id="be4ca-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="be4ca-106">输入</span><span class="sxs-lookup"><span data-stu-id="be4ca-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="be4ca-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="be4ca-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="be4ca-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="be4ca-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="be4ca-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be4ca-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be4ca-110">要转换的操作。</span><span class="sxs-lookup"><span data-stu-id="be4ca-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="be4ca-111">输出： "U => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be4ca-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be4ca-112">新操作 tbat 的 `fn` 输入调用，然后将结果输出传递给 `op` 。</span><span class="sxs-lookup"><span data-stu-id="be4ca-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="be4ca-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="be4ca-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be4ca-114">找</span><span class="sxs-lookup"><span data-stu-id="be4ca-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="be4ca-115">' U</span><span class="sxs-lookup"><span data-stu-id="be4ca-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="be4ca-116">示例</span><span class="sxs-lookup"><span data-stu-id="be4ca-116">Example</span></span>

<span data-ttu-id="be4ca-117">以下调用使用 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 将为输入设计的操作转换 @"Microsoft.Quantum.Arithmetic.BigEndian" 为接受类型为的输入的操作 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：</span><span class="sxs-lookup"><span data-stu-id="be4ca-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="be4ca-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be4ca-118">See Also</span></span>

- [<span data-ttu-id="be4ca-119">Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="be4ca-119">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="be4ca-120">Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="be4ca-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="be4ca-121">Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="be4ca-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="be4ca-122">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="be4ca-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="be4ca-123">Canon。</span><span class="sxs-lookup"><span data-stu-id="be4ca-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)