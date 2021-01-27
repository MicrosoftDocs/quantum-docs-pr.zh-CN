---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840559"
---
# <a name="delayedc-function"></a><span data-ttu-id="9a6d8-102">DelayedC 函数</span><span class="sxs-lookup"><span data-stu-id="9a6d8-102">DelayedC function</span></span>

<span data-ttu-id="9a6d8-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a6d8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a6d8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a6d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a6d8-105">返回应用给定自变量的给定操作的操作。</span><span class="sxs-lookup"><span data-stu-id="9a6d8-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="9a6d8-106">输入</span><span class="sxs-lookup"><span data-stu-id="9a6d8-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="9a6d8-107">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="9a6d8-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9a6d8-108">应用返回值后应用的操作</span><span class="sxs-lookup"><span data-stu-id="9a6d8-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="9a6d8-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="9a6d8-109">arg : 'T</span></span>

<span data-ttu-id="9a6d8-110">将操作应用到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="9a6d8-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="9a6d8-111">输出： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="9a6d8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9a6d8-112">适用于输入的新操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="9a6d8-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9a6d8-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="9a6d8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a6d8-114">找</span><span class="sxs-lookup"><span data-stu-id="9a6d8-114">'T</span></span>

<span data-ttu-id="9a6d8-115">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="9a6d8-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a6d8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a6d8-116">See Also</span></span>

- [<span data-ttu-id="9a6d8-117">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="9a6d8-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="9a6d8-118">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="9a6d8-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)