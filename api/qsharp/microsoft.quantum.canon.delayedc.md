---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206999"
---
# <a name="delayedc-function"></a><span data-ttu-id="f1e52-102">DelayedC 函数</span><span class="sxs-lookup"><span data-stu-id="f1e52-102">DelayedC function</span></span>

<span data-ttu-id="f1e52-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1e52-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1e52-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1e52-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1e52-105">返回应用给定自变量的给定操作的操作。</span><span class="sxs-lookup"><span data-stu-id="f1e52-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f1e52-106">输入</span><span class="sxs-lookup"><span data-stu-id="f1e52-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f1e52-107">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="f1e52-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f1e52-108">应用返回值后应用的操作</span><span class="sxs-lookup"><span data-stu-id="f1e52-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="f1e52-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="f1e52-109">arg : 'T</span></span>

<span data-ttu-id="f1e52-110">将操作应用到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f1e52-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="f1e52-111">输出： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="f1e52-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f1e52-112">适用于输入的新操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="f1e52-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f1e52-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="f1e52-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1e52-114">找</span><span class="sxs-lookup"><span data-stu-id="f1e52-114">'T</span></span>

<span data-ttu-id="f1e52-115">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="f1e52-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1e52-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1e52-116">See Also</span></span>

- [<span data-ttu-id="f1e52-117">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="f1e52-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="f1e52-118">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="f1e52-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)