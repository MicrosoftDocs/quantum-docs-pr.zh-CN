---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216619"
---
# <a name="curriedop-function"></a><span data-ttu-id="f1b06-102">CurriedOp 函数</span><span class="sxs-lookup"><span data-stu-id="f1b06-102">CurriedOp function</span></span>

<span data-ttu-id="f1b06-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1b06-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1b06-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1b06-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1b06-105">返回对两个输入的操作的扩充版本。</span><span class="sxs-lookup"><span data-stu-id="f1b06-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="f1b06-106">也就是说，假设有一个具有两个输入的操作，则此函数将应用咖喱的 isomorphism $f (x，y) \equiv f (x) # B4 y) $ 以返回一个输入的操作，该操作返回一个输入的操作。</span><span class="sxs-lookup"><span data-stu-id="f1b06-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="f1b06-107">输入</span><span class="sxs-lookup"><span data-stu-id="f1b06-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="f1b06-108">op： ( t，' U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1b06-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f1b06-109">其输入为成对的操作。</span><span class="sxs-lookup"><span data-stu-id="f1b06-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="f1b06-110">输出：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1b06-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f1b06-111">一种操作，它接受对的第一个元素，并返回一个接受作为其输入的操作，该操作将原始操作的输入的第二个元素作为输入。</span><span class="sxs-lookup"><span data-stu-id="f1b06-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f1b06-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="f1b06-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1b06-113">找</span><span class="sxs-lookup"><span data-stu-id="f1b06-113">'T</span></span>

<span data-ttu-id="f1b06-114">成对定义的函数的第一个分量的类型。</span><span class="sxs-lookup"><span data-stu-id="f1b06-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="f1b06-115">' U</span><span class="sxs-lookup"><span data-stu-id="f1b06-115">'U</span></span>

<span data-ttu-id="f1b06-116">成对定义的函数的第二个分量的类型。</span><span class="sxs-lookup"><span data-stu-id="f1b06-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1b06-117">备注</span><span class="sxs-lookup"><span data-stu-id="f1b06-117">Remarks</span></span>

<span data-ttu-id="f1b06-118">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="f1b06-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```