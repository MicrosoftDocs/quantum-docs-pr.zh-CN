---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204634"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="50004-102">UncurriedOp 函数</span><span class="sxs-lookup"><span data-stu-id="50004-102">UncurriedOp function</span></span>

<span data-ttu-id="50004-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50004-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50004-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50004-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50004-105">给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。</span><span class="sxs-lookup"><span data-stu-id="50004-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="50004-106">输入</span><span class="sxs-lookup"><span data-stu-id="50004-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="50004-107">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50004-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="50004-108">返回操作的函数。</span><span class="sxs-lookup"><span data-stu-id="50004-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="50004-109">输出： ( t，' U) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50004-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="50004-110">与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="50004-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50004-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="50004-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50004-112">找</span><span class="sxs-lookup"><span data-stu-id="50004-112">'T</span></span>

<span data-ttu-id="50004-113">扩充操作的第一个输入的类型。</span><span class="sxs-lookup"><span data-stu-id="50004-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="50004-114">' U</span><span class="sxs-lookup"><span data-stu-id="50004-114">'U</span></span>

<span data-ttu-id="50004-115">扩充操作的第二个输入的类型。</span><span class="sxs-lookup"><span data-stu-id="50004-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="50004-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50004-116">See Also</span></span>

- [<span data-ttu-id="50004-117">Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="50004-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="50004-118">Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="50004-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="50004-119">Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="50004-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)