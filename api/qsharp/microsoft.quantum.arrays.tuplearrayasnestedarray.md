---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696445"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="0d17f-102">TupleArrayAsNestedArray 函数</span><span class="sxs-lookup"><span data-stu-id="0d17f-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="0d17f-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0d17f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0d17f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d17f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d17f-105">将2元组的列表转换为嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="0d17f-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="0d17f-106">输入</span><span class="sxs-lookup"><span data-stu-id="0d17f-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="0d17f-107">tupleList： ( t，不) []</span><span class="sxs-lookup"><span data-stu-id="0d17f-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="0d17f-108">要转换为嵌套数组的2元组的列表。</span><span class="sxs-lookup"><span data-stu-id="0d17f-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="0d17f-109">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="0d17f-109">Output : 'T[][]</span></span>

<span data-ttu-id="0d17f-110">长度与 tupleList 匹配的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="0d17f-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="0d17f-111">示例</span><span class="sxs-lookup"><span data-stu-id="0d17f-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="0d17f-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="0d17f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d17f-113">找</span><span class="sxs-lookup"><span data-stu-id="0d17f-113">'T</span></span>

