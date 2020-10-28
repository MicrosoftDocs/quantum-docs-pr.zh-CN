---
uid: Microsoft.Quantum.Canon.DelayedA
title: DelayedA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696065"
---
# <a name="delayeda-function"></a><span data-ttu-id="aee56-102">DelayedA 函数</span><span class="sxs-lookup"><span data-stu-id="aee56-102">DelayedA function</span></span>

<span data-ttu-id="aee56-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aee56-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aee56-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aee56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aee56-105">返回应用给定自变量的给定操作的操作。</span><span class="sxs-lookup"><span data-stu-id="aee56-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="aee56-106">输入</span><span class="sxs-lookup"><span data-stu-id="aee56-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="aee56-107">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="aee56-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aee56-108">应用返回值后应用的操作</span><span class="sxs-lookup"><span data-stu-id="aee56-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="aee56-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="aee56-109">arg : 'T</span></span>

<span data-ttu-id="aee56-110">将操作应用到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="aee56-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="aee56-111">输出： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整</span><span class="sxs-lookup"><span data-stu-id="aee56-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aee56-112">适用于输入的新操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="aee56-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aee56-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="aee56-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aee56-114">找</span><span class="sxs-lookup"><span data-stu-id="aee56-114">'T</span></span>

<span data-ttu-id="aee56-115">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="aee56-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="aee56-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aee56-116">See Also</span></span>

- [<span data-ttu-id="aee56-117">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="aee56-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="aee56-118">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="aee56-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)