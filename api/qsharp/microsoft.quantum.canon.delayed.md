---
uid: Microsoft.Quantum.Canon.Delayed
title: 延迟函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840586"
---
# <a name="delayed-function"></a><span data-ttu-id="76fe0-102">延迟函数</span><span class="sxs-lookup"><span data-stu-id="76fe0-102">Delayed function</span></span>

<span data-ttu-id="76fe0-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76fe0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76fe0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76fe0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76fe0-105">返回应用给定自变量的给定操作的操作。</span><span class="sxs-lookup"><span data-stu-id="76fe0-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="76fe0-106">输入</span><span class="sxs-lookup"><span data-stu-id="76fe0-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="76fe0-107">op： t => ' U</span><span class="sxs-lookup"><span data-stu-id="76fe0-107">op : 'T => 'U</span></span> 

<span data-ttu-id="76fe0-108">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="76fe0-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="76fe0-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="76fe0-109">arg : 'T</span></span>

<span data-ttu-id="76fe0-110">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="76fe0-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="76fe0-111">输出： [Unit](xref:microsoft.quantum.lang-ref.unit) => "U</span><span class="sxs-lookup"><span data-stu-id="76fe0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="76fe0-112">适用于输入的新操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="76fe0-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="76fe0-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="76fe0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76fe0-114">找</span><span class="sxs-lookup"><span data-stu-id="76fe0-114">'T</span></span>

<span data-ttu-id="76fe0-115">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="76fe0-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="76fe0-116">' U</span><span class="sxs-lookup"><span data-stu-id="76fe0-116">'U</span></span>

<span data-ttu-id="76fe0-117">要延迟的操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="76fe0-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="76fe0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76fe0-118">See Also</span></span>

- [<span data-ttu-id="76fe0-119">Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="76fe0-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="76fe0-120">Canon. DelayedA</span><span class="sxs-lookup"><span data-stu-id="76fe0-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="76fe0-121">Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="76fe0-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="76fe0-122">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="76fe0-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)