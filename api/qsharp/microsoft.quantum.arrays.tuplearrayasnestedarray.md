---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845396"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="85c61-102">TupleArrayAsNestedArray 函数</span><span class="sxs-lookup"><span data-stu-id="85c61-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="85c61-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="85c61-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="85c61-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85c61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85c61-105">将2元组的列表转换为嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="85c61-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="85c61-106">输入</span><span class="sxs-lookup"><span data-stu-id="85c61-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="85c61-107">tupleList： ( t，不) []</span><span class="sxs-lookup"><span data-stu-id="85c61-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="85c61-108">要转换为嵌套数组的2元组的列表。</span><span class="sxs-lookup"><span data-stu-id="85c61-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="85c61-109">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="85c61-109">Output : 'T[][]</span></span>

<span data-ttu-id="85c61-110">长度与 tupleList 匹配的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="85c61-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="85c61-111">示例</span><span class="sxs-lookup"><span data-stu-id="85c61-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="85c61-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="85c61-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85c61-113">找</span><span class="sxs-lookup"><span data-stu-id="85c61-113">'T</span></span>

