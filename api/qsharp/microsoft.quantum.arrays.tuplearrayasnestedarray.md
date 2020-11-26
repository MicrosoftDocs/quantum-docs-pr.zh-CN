---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: c898178b6385b27f753509f0748a8b666b5066bd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220070"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="c9080-102">TupleArrayAsNestedArray 函数</span><span class="sxs-lookup"><span data-stu-id="c9080-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="c9080-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c9080-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c9080-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9080-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9080-105">将2元组的列表转换为嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="c9080-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="c9080-106">输入</span><span class="sxs-lookup"><span data-stu-id="c9080-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="c9080-107">tupleList： ( t，不) []</span><span class="sxs-lookup"><span data-stu-id="c9080-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="c9080-108">要转换为嵌套数组的2元组的列表。</span><span class="sxs-lookup"><span data-stu-id="c9080-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="c9080-109">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="c9080-109">Output : 'T[][]</span></span>

<span data-ttu-id="c9080-110">长度与 tupleList 匹配的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="c9080-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="c9080-111">示例</span><span class="sxs-lookup"><span data-stu-id="c9080-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="c9080-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="c9080-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9080-113">找</span><span class="sxs-lookup"><span data-stu-id="c9080-113">'T</span></span>

