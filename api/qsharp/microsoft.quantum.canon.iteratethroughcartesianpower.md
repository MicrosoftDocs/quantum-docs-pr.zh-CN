---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206470"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="9ba08-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="9ba08-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="9ba08-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ba08-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ba08-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ba08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ba08-105">以整数范围的笛卡尔幂对每个索引应用操作。</span><span class="sxs-lookup"><span data-stu-id="9ba08-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="9ba08-106">描述</span><span class="sxs-lookup"><span data-stu-id="9ba08-106">Description</span></span>

<span data-ttu-id="9ba08-107">以迭代方式为范围的笛卡尔幂的每个元素应用操作 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="9ba08-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="9ba08-108">输入</span><span class="sxs-lookup"><span data-stu-id="9ba08-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="9ba08-109">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ba08-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9ba08-110">应为范围增加的笛卡尔幂 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="9ba08-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="9ba08-111">绑定： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ba08-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9ba08-112">要循环访问的范围的规范，给定为范围的长度。</span><span class="sxs-lookup"><span data-stu-id="9ba08-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="9ba08-113">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ba08-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9ba08-114">为给定笛卡尔幂的每个元素调用的操作。</span><span class="sxs-lookup"><span data-stu-id="9ba08-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ba08-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ba08-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9ba08-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ba08-116">See Also</span></span>

- [<span data-ttu-id="9ba08-117">Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="9ba08-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)