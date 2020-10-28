---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696543"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="b6869-102">CumulativeFolded 函数</span><span class="sxs-lookup"><span data-stu-id="b6869-102">CumulativeFolded function</span></span>

<span data-ttu-id="b6869-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b6869-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b6869-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6869-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6869-105">将映射和折叠合并为一个函数</span><span class="sxs-lookup"><span data-stu-id="b6869-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="b6869-106">说明</span><span class="sxs-lookup"><span data-stu-id="b6869-106">Description</span></span>

<span data-ttu-id="b6869-107">此函数 `fn` 通过数组来循环访问函数，从初始状态开始， `state` 返回所有中间值，不包括初始状态。</span><span class="sxs-lookup"><span data-stu-id="b6869-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="b6869-108">输入</span><span class="sxs-lookup"><span data-stu-id="b6869-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="b6869-109">fn： ( 状态，不) > "状态</span><span class="sxs-lookup"><span data-stu-id="b6869-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="b6869-110">要在数组上折叠的函数</span><span class="sxs-lookup"><span data-stu-id="b6869-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="b6869-111">状态： "状态"</span><span class="sxs-lookup"><span data-stu-id="b6869-111">state : 'State</span></span>

<span data-ttu-id="b6869-112">要折叠的初始状态</span><span class="sxs-lookup"><span data-stu-id="b6869-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="b6869-113">array： t []</span><span class="sxs-lookup"><span data-stu-id="b6869-113">array : 'T[]</span></span>

<span data-ttu-id="b6869-114">要折叠的值数组</span><span class="sxs-lookup"><span data-stu-id="b6869-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="b6869-115">输出： "State []</span><span class="sxs-lookup"><span data-stu-id="b6869-115">Output : 'State[]</span></span>

<span data-ttu-id="b6869-116">所有中间状态，包括最终状态，但不包括初始状态。</span><span class="sxs-lookup"><span data-stu-id="b6869-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="b6869-117">输出数组的长度与相同 `array` 。</span><span class="sxs-lookup"><span data-stu-id="b6869-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b6869-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="b6869-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="b6869-119">"状态</span><span class="sxs-lookup"><span data-stu-id="b6869-119">'State</span></span>

<span data-ttu-id="b6869-120">函数操作的状态的类型 `fn` ，即接受作为其第一个输入并返回。</span><span class="sxs-lookup"><span data-stu-id="b6869-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="b6869-121">找</span><span class="sxs-lookup"><span data-stu-id="b6869-121">'T</span></span>

<span data-ttu-id="b6869-122">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="b6869-122">The type of `array` elements.</span></span>