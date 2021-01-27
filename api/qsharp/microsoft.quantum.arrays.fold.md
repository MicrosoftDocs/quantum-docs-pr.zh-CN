---
uid: Microsoft.Quantum.Arrays.Fold
title: 折页函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848608"
---
# <a name="fold-function"></a><span data-ttu-id="018f4-102">折页函数</span><span class="sxs-lookup"><span data-stu-id="018f4-102">Fold function</span></span>

<span data-ttu-id="018f4-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="018f4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="018f4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="018f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="018f4-105">通过数组循环访问函数 `f` `array` ，返回 `f(f(f(initialState, array[0]), array[1]), ...)` 。</span><span class="sxs-lookup"><span data-stu-id="018f4-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="018f4-106">输入</span><span class="sxs-lookup"><span data-stu-id="018f4-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="018f4-107">文件夹： ( "状态，不) ->" 状态</span><span class="sxs-lookup"><span data-stu-id="018f4-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="018f4-108">要在数组上折叠的函数。</span><span class="sxs-lookup"><span data-stu-id="018f4-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="018f4-109">状态： "状态"</span><span class="sxs-lookup"><span data-stu-id="018f4-109">state : 'State</span></span>

<span data-ttu-id="018f4-110">文件夹的初始状态。</span><span class="sxs-lookup"><span data-stu-id="018f4-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="018f4-111">array： t []</span><span class="sxs-lookup"><span data-stu-id="018f4-111">array : 'T[]</span></span>

<span data-ttu-id="018f4-112">要折叠的值的数组。</span><span class="sxs-lookup"><span data-stu-id="018f4-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="018f4-113">输出： "状态</span><span class="sxs-lookup"><span data-stu-id="018f4-113">Output : 'State</span></span>

<span data-ttu-id="018f4-114">遍历的所有元素后，文件夹返回的最终状态 `array` 。</span><span class="sxs-lookup"><span data-stu-id="018f4-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="018f4-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="018f4-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="018f4-116">"状态</span><span class="sxs-lookup"><span data-stu-id="018f4-116">'State</span></span>

<span data-ttu-id="018f4-117">函数操作的状态的类型 `folder` ，即接受作为其第一个参数，并返回。</span><span class="sxs-lookup"><span data-stu-id="018f4-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="018f4-118">找</span><span class="sxs-lookup"><span data-stu-id="018f4-118">'T</span></span>

<span data-ttu-id="018f4-119">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="018f4-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="018f4-120">示例</span><span class="sxs-lookup"><span data-stu-id="018f4-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```