---
uid: Microsoft.Quantum.Arrays.Fold
title: 折页函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221158"
---
# <a name="fold-function"></a><span data-ttu-id="63a2a-102">折页函数</span><span class="sxs-lookup"><span data-stu-id="63a2a-102">Fold function</span></span>

<span data-ttu-id="63a2a-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="63a2a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="63a2a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63a2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63a2a-105">通过数组循环访问函数 `f` `array` ，返回 `f(f(f(initialState, array[0]), array[1]), ...)` 。</span><span class="sxs-lookup"><span data-stu-id="63a2a-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="63a2a-106">输入</span><span class="sxs-lookup"><span data-stu-id="63a2a-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="63a2a-107">文件夹： ( "状态，不) ->" 状态</span><span class="sxs-lookup"><span data-stu-id="63a2a-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="63a2a-108">要在数组上折叠的函数。</span><span class="sxs-lookup"><span data-stu-id="63a2a-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="63a2a-109">状态： "状态"</span><span class="sxs-lookup"><span data-stu-id="63a2a-109">state : 'State</span></span>

<span data-ttu-id="63a2a-110">文件夹的初始状态。</span><span class="sxs-lookup"><span data-stu-id="63a2a-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="63a2a-111">array： t []</span><span class="sxs-lookup"><span data-stu-id="63a2a-111">array : 'T[]</span></span>

<span data-ttu-id="63a2a-112">要折叠的值的数组。</span><span class="sxs-lookup"><span data-stu-id="63a2a-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="63a2a-113">输出： "状态</span><span class="sxs-lookup"><span data-stu-id="63a2a-113">Output : 'State</span></span>

<span data-ttu-id="63a2a-114">遍历的所有元素后，文件夹返回的最终状态 `array` 。</span><span class="sxs-lookup"><span data-stu-id="63a2a-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63a2a-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="63a2a-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="63a2a-116">"状态</span><span class="sxs-lookup"><span data-stu-id="63a2a-116">'State</span></span>

<span data-ttu-id="63a2a-117">函数操作的状态的类型 `folder` ，即接受作为其第一个参数，并返回。</span><span class="sxs-lookup"><span data-stu-id="63a2a-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="63a2a-118">找</span><span class="sxs-lookup"><span data-stu-id="63a2a-118">'T</span></span>

<span data-ttu-id="63a2a-119">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="63a2a-119">The type of `array` elements.</span></span>