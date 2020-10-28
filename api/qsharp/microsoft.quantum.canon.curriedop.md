---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696082"
---
# <a name="curriedop-function"></a><span data-ttu-id="57526-102">CurriedOp 函数</span><span class="sxs-lookup"><span data-stu-id="57526-102">CurriedOp function</span></span>

<span data-ttu-id="57526-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57526-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57526-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57526-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57526-105">返回对两个输入的操作的扩充版本。</span><span class="sxs-lookup"><span data-stu-id="57526-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="57526-106">也就是说，假设有一个具有两个输入的操作，则此函数将应用咖喱的 isomorphism $f (x，y) \equiv f (x) # B4 y) $ 以返回一个输入的操作，该操作返回一个输入的操作。</span><span class="sxs-lookup"><span data-stu-id="57526-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="57526-107">输入</span><span class="sxs-lookup"><span data-stu-id="57526-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="57526-108">op： ( t，' U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57526-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="57526-109">其输入为成对的操作。</span><span class="sxs-lookup"><span data-stu-id="57526-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="57526-110">输出：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57526-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="57526-111">一种操作，它接受对的第一个元素，并返回一个接受作为其输入的操作，该操作将原始操作的输入的第二个元素作为输入。</span><span class="sxs-lookup"><span data-stu-id="57526-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="57526-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="57526-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57526-113">找</span><span class="sxs-lookup"><span data-stu-id="57526-113">'T</span></span>

<span data-ttu-id="57526-114">成对定义的函数的第一个分量的类型。</span><span class="sxs-lookup"><span data-stu-id="57526-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="57526-115">' U</span><span class="sxs-lookup"><span data-stu-id="57526-115">'U</span></span>

<span data-ttu-id="57526-116">成对定义的函数的第二个分量的类型。</span><span class="sxs-lookup"><span data-stu-id="57526-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="57526-117">注解</span><span class="sxs-lookup"><span data-stu-id="57526-117">Remarks</span></span>

<span data-ttu-id="57526-118">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="57526-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```