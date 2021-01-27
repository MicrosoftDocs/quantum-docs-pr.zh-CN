---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840145"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="05529-102">TransformedOperationA 函数</span><span class="sxs-lookup"><span data-stu-id="05529-102">TransformedOperationA function</span></span>

<span data-ttu-id="05529-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05529-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05529-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05529-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05529-105">给定一个函数和一个操作，返回一个新的操作，其输入由给定函数转换。</span><span class="sxs-lookup"><span data-stu-id="05529-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="05529-106">输入</span><span class="sxs-lookup"><span data-stu-id="05529-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="05529-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="05529-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="05529-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="05529-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="05529-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="05529-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="05529-110">要转换的操作。</span><span class="sxs-lookup"><span data-stu-id="05529-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="05529-111">输出： "U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="05529-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="05529-112">新操作 tbat 的 `fn` 输入调用，然后将结果输出传递给 `op` 。</span><span class="sxs-lookup"><span data-stu-id="05529-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="05529-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="05529-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="05529-114">找</span><span class="sxs-lookup"><span data-stu-id="05529-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="05529-115">' U</span><span class="sxs-lookup"><span data-stu-id="05529-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="05529-116">示例</span><span class="sxs-lookup"><span data-stu-id="05529-116">Example</span></span>

<span data-ttu-id="05529-117">以下调用使用 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 将为输入设计的操作转换 @"Microsoft.Quantum.Arithmetic.BigEndian" 为接受类型为的输入的操作 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：</span><span class="sxs-lookup"><span data-stu-id="05529-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="05529-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05529-118">See Also</span></span>

- [<span data-ttu-id="05529-119">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="05529-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="05529-120">Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="05529-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="05529-121">Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="05529-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="05529-122">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="05529-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="05529-123">Canon。</span><span class="sxs-lookup"><span data-stu-id="05529-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)