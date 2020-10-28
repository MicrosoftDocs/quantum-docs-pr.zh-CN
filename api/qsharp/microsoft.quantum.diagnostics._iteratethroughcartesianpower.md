---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695621"
---
# <a name="_iteratethroughcartesianpower-operation"></a><span data-ttu-id="648ac-102">_iterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="648ac-102">_iterateThroughCartesianPower operation</span></span>

<span data-ttu-id="648ac-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="648ac-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="648ac-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="648ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="648ac-105">通过笛卡尔积 [0，界限 [0]-1] × [0，界限 [1]-1] × [0，界限 [Length (界限) -1]-1] 来循环访问变量，并为笛卡尔积的每个元素调用 op (arr) </span><span class="sxs-lookup"><span data-stu-id="648ac-105">Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product</span></span>

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="648ac-106">输入</span><span class="sxs-lookup"><span data-stu-id="648ac-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="648ac-107">长度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="648ac-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="value--int"></a><span data-ttu-id="648ac-108">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="648ac-108">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--int--unit"></a><span data-ttu-id="648ac-109">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="648ac-109">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="648ac-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="648ac-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

