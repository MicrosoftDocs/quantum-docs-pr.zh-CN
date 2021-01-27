---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840299"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="28248-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="28248-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="28248-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28248-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28248-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28248-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28248-105">以整数范围的笛卡尔幂对每个索引应用操作。</span><span class="sxs-lookup"><span data-stu-id="28248-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="28248-106">说明</span><span class="sxs-lookup"><span data-stu-id="28248-106">Description</span></span>

<span data-ttu-id="28248-107">以迭代方式为范围的笛卡尔幂的每个元素应用操作 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="28248-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="28248-108">输入</span><span class="sxs-lookup"><span data-stu-id="28248-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="28248-109">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28248-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28248-110">应为范围增加的笛卡尔幂 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="28248-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="28248-111">绑定： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28248-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28248-112">要循环访问的范围的规范，给定为范围的长度。</span><span class="sxs-lookup"><span data-stu-id="28248-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="28248-113">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28248-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="28248-114">为给定笛卡尔幂的每个元素调用的操作。</span><span class="sxs-lookup"><span data-stu-id="28248-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28248-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28248-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="28248-116">示例</span><span class="sxs-lookup"><span data-stu-id="28248-116">Example</span></span>

<span data-ttu-id="28248-117">给定一个操作 `op` ，以下两个代码段是等效的：</span><span class="sxs-lookup"><span data-stu-id="28248-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="28248-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28248-118">See Also</span></span>

- [<span data-ttu-id="28248-119">Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="28248-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)