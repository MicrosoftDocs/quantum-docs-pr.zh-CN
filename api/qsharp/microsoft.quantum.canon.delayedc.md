---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696060"
---
# <a name="delayedc-function"></a><span data-ttu-id="aa63b-102">DelayedC 函数</span><span class="sxs-lookup"><span data-stu-id="aa63b-102">DelayedC function</span></span>

<span data-ttu-id="aa63b-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa63b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa63b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa63b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa63b-105">返回应用给定自变量的给定操作的操作。</span><span class="sxs-lookup"><span data-stu-id="aa63b-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="aa63b-106">输入</span><span class="sxs-lookup"><span data-stu-id="aa63b-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="aa63b-107">op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="aa63b-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="aa63b-108">应用返回值后应用的操作</span><span class="sxs-lookup"><span data-stu-id="aa63b-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="aa63b-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="aa63b-109">arg : 'T</span></span>

<span data-ttu-id="aa63b-110">将操作应用到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="aa63b-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="aa63b-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="aa63b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="aa63b-112">适用于输入的新操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="aa63b-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aa63b-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="aa63b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa63b-114">找</span><span class="sxs-lookup"><span data-stu-id="aa63b-114">'T</span></span>

<span data-ttu-id="aa63b-115">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="aa63b-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa63b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa63b-116">See Also</span></span>

- [<span data-ttu-id="aa63b-117">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="aa63b-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="aa63b-118">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="aa63b-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)