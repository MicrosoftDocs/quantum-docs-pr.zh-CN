---
uid: Microsoft.Quantum.Arrays.Fold
title: 折页函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696512"
---
# <a name="fold-function"></a><span data-ttu-id="c3dcc-102">折页函数</span><span class="sxs-lookup"><span data-stu-id="c3dcc-102">Fold function</span></span>

<span data-ttu-id="c3dcc-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3dcc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3dcc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3dcc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3dcc-105">通过数组循环访问函数 `f` `array` ，返回 `f(f(f(initialState, array[0]), array[1]), ...)` 。</span><span class="sxs-lookup"><span data-stu-id="c3dcc-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="c3dcc-106">输入</span><span class="sxs-lookup"><span data-stu-id="c3dcc-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="c3dcc-107">文件夹： ( "状态，不) ->" 状态</span><span class="sxs-lookup"><span data-stu-id="c3dcc-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="c3dcc-108">要在数组上折叠的函数。</span><span class="sxs-lookup"><span data-stu-id="c3dcc-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="c3dcc-109">状态： "状态"</span><span class="sxs-lookup"><span data-stu-id="c3dcc-109">state : 'State</span></span>

<span data-ttu-id="c3dcc-110">文件夹的初始状态。</span><span class="sxs-lookup"><span data-stu-id="c3dcc-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="c3dcc-111">array： t []</span><span class="sxs-lookup"><span data-stu-id="c3dcc-111">array : 'T[]</span></span>

<span data-ttu-id="c3dcc-112">要折叠的值的数组。</span><span class="sxs-lookup"><span data-stu-id="c3dcc-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="c3dcc-113">输出： "状态</span><span class="sxs-lookup"><span data-stu-id="c3dcc-113">Output : 'State</span></span>

<span data-ttu-id="c3dcc-114">遍历的所有元素后，文件夹返回的最终状态 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c3dcc-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3dcc-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="c3dcc-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="c3dcc-116">"状态</span><span class="sxs-lookup"><span data-stu-id="c3dcc-116">'State</span></span>

<span data-ttu-id="c3dcc-117">函数操作的状态的类型 `folder` ，即接受作为其第一个参数，并返回。</span><span class="sxs-lookup"><span data-stu-id="c3dcc-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="c3dcc-118">找</span><span class="sxs-lookup"><span data-stu-id="c3dcc-118">'T</span></span>

<span data-ttu-id="c3dcc-119">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c3dcc-119">The type of `array` elements.</span></span>