---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204583"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="8bf7f-102">UncurriedOpC 函数</span><span class="sxs-lookup"><span data-stu-id="8bf7f-102">UncurriedOpC function</span></span>

<span data-ttu-id="8bf7f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8bf7f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8bf7f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8bf7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8bf7f-105">给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。</span><span class="sxs-lookup"><span data-stu-id="8bf7f-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="8bf7f-106">修饰符 `C` 指示操作可以控制。</span><span class="sxs-lookup"><span data-stu-id="8bf7f-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="8bf7f-107">输入</span><span class="sxs-lookup"><span data-stu-id="8bf7f-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="8bf7f-108">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="8bf7f-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8bf7f-109">返回操作的函数。</span><span class="sxs-lookup"><span data-stu-id="8bf7f-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="8bf7f-110">输出： ( t，' U) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="8bf7f-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8bf7f-111">与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="8bf7f-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8bf7f-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="8bf7f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8bf7f-113">找</span><span class="sxs-lookup"><span data-stu-id="8bf7f-113">'T</span></span>

<span data-ttu-id="8bf7f-114">扩充函数第一个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="8bf7f-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="8bf7f-115">' U</span><span class="sxs-lookup"><span data-stu-id="8bf7f-115">'U</span></span>

<span data-ttu-id="8bf7f-116">扩充函数的第二个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="8bf7f-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bf7f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bf7f-117">See Also</span></span>

- [<span data-ttu-id="8bf7f-118">Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="8bf7f-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)