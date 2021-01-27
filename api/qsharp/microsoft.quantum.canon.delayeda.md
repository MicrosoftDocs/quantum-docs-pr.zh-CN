---
uid: Microsoft.Quantum.Canon.DelayedA
title: DelayedA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: e53279bd3ddc5fa8bc0c862f998b273a9e17a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840598"
---
# <a name="delayeda-function"></a><span data-ttu-id="8346c-102">DelayedA 函数</span><span class="sxs-lookup"><span data-stu-id="8346c-102">DelayedA function</span></span>

<span data-ttu-id="8346c-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8346c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8346c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8346c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8346c-105">返回应用给定自变量的给定操作的操作。</span><span class="sxs-lookup"><span data-stu-id="8346c-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="8346c-106">输入</span><span class="sxs-lookup"><span data-stu-id="8346c-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="8346c-107">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="8346c-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8346c-108">应用返回值后应用的操作</span><span class="sxs-lookup"><span data-stu-id="8346c-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="8346c-109">arg： t</span><span class="sxs-lookup"><span data-stu-id="8346c-109">arg : 'T</span></span>

<span data-ttu-id="8346c-110">将操作应用到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="8346c-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="8346c-111">输出： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="8346c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8346c-112">适用于输入的新操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="8346c-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8346c-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="8346c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8346c-114">找</span><span class="sxs-lookup"><span data-stu-id="8346c-114">'T</span></span>

<span data-ttu-id="8346c-115">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="8346c-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="8346c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8346c-116">See Also</span></span>

- [<span data-ttu-id="8346c-117">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="8346c-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="8346c-118">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="8346c-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)