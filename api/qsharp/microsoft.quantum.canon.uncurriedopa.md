---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695918"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="471ab-102">UncurriedOpA 函数</span><span class="sxs-lookup"><span data-stu-id="471ab-102">UncurriedOpA function</span></span>

<span data-ttu-id="471ab-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="471ab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="471ab-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="471ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="471ab-105">给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。</span><span class="sxs-lookup"><span data-stu-id="471ab-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="471ab-106">修饰符 `A` 指示操作是 adjointable 的。</span><span class="sxs-lookup"><span data-stu-id="471ab-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="471ab-107">输入</span><span class="sxs-lookup"><span data-stu-id="471ab-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="471ab-108">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="471ab-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="471ab-109">返回操作的函数。</span><span class="sxs-lookup"><span data-stu-id="471ab-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="471ab-110">输出： ( t，' U) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="471ab-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="471ab-111">与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="471ab-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="471ab-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="471ab-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="471ab-113">找</span><span class="sxs-lookup"><span data-stu-id="471ab-113">'T</span></span>

<span data-ttu-id="471ab-114">扩充函数第一个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="471ab-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="471ab-115">' U</span><span class="sxs-lookup"><span data-stu-id="471ab-115">'U</span></span>

<span data-ttu-id="471ab-116">扩充函数的第二个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="471ab-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="471ab-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="471ab-117">See Also</span></span>

- [<span data-ttu-id="471ab-118">Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="471ab-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)