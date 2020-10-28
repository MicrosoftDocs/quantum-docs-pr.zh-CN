---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696033"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="0da49-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="0da49-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="0da49-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0da49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0da49-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0da49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0da49-105">以整数范围的笛卡尔幂对每个索引应用操作。</span><span class="sxs-lookup"><span data-stu-id="0da49-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="0da49-106">说明</span><span class="sxs-lookup"><span data-stu-id="0da49-106">Description</span></span>

<span data-ttu-id="0da49-107">以迭代方式为范围的笛卡尔幂的每个元素应用操作 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="0da49-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="0da49-108">输入</span><span class="sxs-lookup"><span data-stu-id="0da49-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="0da49-109">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0da49-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0da49-110">应为范围增加的笛卡尔幂 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="0da49-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="0da49-111">绑定： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0da49-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0da49-112">要循环访问的范围的规范，给定为范围的长度。</span><span class="sxs-lookup"><span data-stu-id="0da49-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="0da49-113">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0da49-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0da49-114">为给定笛卡尔幂的每个元素调用的操作。</span><span class="sxs-lookup"><span data-stu-id="0da49-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0da49-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0da49-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0da49-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0da49-116">See Also</span></span>

- [<span data-ttu-id="0da49-117">Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="0da49-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)