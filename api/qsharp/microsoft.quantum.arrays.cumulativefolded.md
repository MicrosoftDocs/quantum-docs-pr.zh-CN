---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846248"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="b034e-102">CumulativeFolded 函数</span><span class="sxs-lookup"><span data-stu-id="b034e-102">CumulativeFolded function</span></span>

<span data-ttu-id="b034e-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b034e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b034e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b034e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b034e-105">将映射和折叠合并为一个函数</span><span class="sxs-lookup"><span data-stu-id="b034e-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="b034e-106">说明</span><span class="sxs-lookup"><span data-stu-id="b034e-106">Description</span></span>

<span data-ttu-id="b034e-107">此函数 `fn` 通过数组来循环访问函数，从初始状态开始， `state` 返回所有中间值，不包括初始状态。</span><span class="sxs-lookup"><span data-stu-id="b034e-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="b034e-108">输入</span><span class="sxs-lookup"><span data-stu-id="b034e-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="b034e-109">fn： ( 状态，不) > "状态</span><span class="sxs-lookup"><span data-stu-id="b034e-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="b034e-110">要在数组上折叠的函数</span><span class="sxs-lookup"><span data-stu-id="b034e-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="b034e-111">状态： "状态"</span><span class="sxs-lookup"><span data-stu-id="b034e-111">state : 'State</span></span>

<span data-ttu-id="b034e-112">要折叠的初始状态</span><span class="sxs-lookup"><span data-stu-id="b034e-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="b034e-113">array： t []</span><span class="sxs-lookup"><span data-stu-id="b034e-113">array : 'T[]</span></span>

<span data-ttu-id="b034e-114">要折叠的值数组</span><span class="sxs-lookup"><span data-stu-id="b034e-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="b034e-115">输出： "State []</span><span class="sxs-lookup"><span data-stu-id="b034e-115">Output : 'State[]</span></span>

<span data-ttu-id="b034e-116">所有中间状态，包括最终状态，但不包括初始状态。</span><span class="sxs-lookup"><span data-stu-id="b034e-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="b034e-117">输出数组的长度与相同 `array` 。</span><span class="sxs-lookup"><span data-stu-id="b034e-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b034e-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="b034e-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="b034e-119">"状态</span><span class="sxs-lookup"><span data-stu-id="b034e-119">'State</span></span>

<span data-ttu-id="b034e-120">函数操作的状态的类型 `fn` ，即接受作为其第一个输入并返回。</span><span class="sxs-lookup"><span data-stu-id="b034e-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="b034e-121">找</span><span class="sxs-lookup"><span data-stu-id="b034e-121">'T</span></span>

<span data-ttu-id="b034e-122">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="b034e-122">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="b034e-123">示例</span><span class="sxs-lookup"><span data-stu-id="b034e-123">Example</span></span>

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```