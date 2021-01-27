---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851992"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="42123-102">UncurriedOpC 函数</span><span class="sxs-lookup"><span data-stu-id="42123-102">UncurriedOpC function</span></span>

<span data-ttu-id="42123-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42123-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42123-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42123-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42123-105">给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。</span><span class="sxs-lookup"><span data-stu-id="42123-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="42123-106">修饰符 `C` 指示操作可以控制。</span><span class="sxs-lookup"><span data-stu-id="42123-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="42123-107">输入</span><span class="sxs-lookup"><span data-stu-id="42123-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="42123-108">curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="42123-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="42123-109">返回操作的函数。</span><span class="sxs-lookup"><span data-stu-id="42123-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="42123-110">输出： ( t，' U) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="42123-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="42123-111">与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="42123-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="42123-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="42123-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42123-113">找</span><span class="sxs-lookup"><span data-stu-id="42123-113">'T</span></span>

<span data-ttu-id="42123-114">扩充函数第一个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="42123-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="42123-115">' U</span><span class="sxs-lookup"><span data-stu-id="42123-115">'U</span></span>

<span data-ttu-id="42123-116">扩充函数的第二个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="42123-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="42123-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42123-117">See Also</span></span>

- [<span data-ttu-id="42123-118">Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="42123-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)