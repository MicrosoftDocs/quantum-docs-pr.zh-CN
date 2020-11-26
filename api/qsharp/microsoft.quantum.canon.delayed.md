---
uid: Microsoft.Quantum.Canon.Delayed
title: 延迟函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216449"
---
# <a name="delayed-function"></a><span data-ttu-id="a3301-102">延迟函数</span><span class="sxs-lookup"><span data-stu-id="a3301-102">Delayed function</span></span>

<span data-ttu-id="a3301-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3301-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3301-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3301-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3301-105">返回应用给定自变量的给定操作的操作。</span><span class="sxs-lookup"><span data-stu-id="a3301-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="a3301-106">输入</span><span class="sxs-lookup"><span data-stu-id="a3301-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="a3301-107">op： t => ' U</span><span class="sxs-lookup"><span data-stu-id="a3301-107">op : 'T => 'U</span></span> 

<span data-ttu-id="a3301-108">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="a3301-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="a3301-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="a3301-109">arg : 'T</span></span>

<span data-ttu-id="a3301-110">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="a3301-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="a3301-111">输出： [Unit](xref:microsoft.quantum.lang-ref.unit) => "U</span><span class="sxs-lookup"><span data-stu-id="a3301-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="a3301-112">适用于输入的新操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="a3301-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a3301-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="a3301-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3301-114">找</span><span class="sxs-lookup"><span data-stu-id="a3301-114">'T</span></span>

<span data-ttu-id="a3301-115">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="a3301-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="a3301-116">' U</span><span class="sxs-lookup"><span data-stu-id="a3301-116">'U</span></span>

<span data-ttu-id="a3301-117">要延迟的操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="a3301-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3301-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3301-118">See Also</span></span>

- [<span data-ttu-id="a3301-119">Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="a3301-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="a3301-120">Canon. DelayedA</span><span class="sxs-lookup"><span data-stu-id="a3301-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="a3301-121">Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="a3301-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="a3301-122">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="a3301-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)