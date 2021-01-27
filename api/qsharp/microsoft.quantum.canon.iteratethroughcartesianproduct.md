---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840284"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="fc01e-102">IterateThroughCartesianProduct 操作</span><span class="sxs-lookup"><span data-stu-id="fc01e-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="fc01e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fc01e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fc01e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc01e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc01e-105">对若干范围内笛卡尔积中的每个索引应用操作。</span><span class="sxs-lookup"><span data-stu-id="fc01e-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="fc01e-106">说明</span><span class="sxs-lookup"><span data-stu-id="fc01e-106">Description</span></span>

<span data-ttu-id="fc01e-107">以迭代方式为、、... 的笛卡尔积的每个元素应用操作 `0..(bounds[0] - 1)` `0..(bounds[1] - 1)``0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="fc01e-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="fc01e-108">输入</span><span class="sxs-lookup"><span data-stu-id="fc01e-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="fc01e-109">界限： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fc01e-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fc01e-110">指定要循环访问的范围的数组，其中每个范围都指定为整数长度。</span><span class="sxs-lookup"><span data-stu-id="fc01e-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="fc01e-111">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc01e-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fc01e-112">为给定笛卡尔积的每个元素调用的操作。</span><span class="sxs-lookup"><span data-stu-id="fc01e-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc01e-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc01e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="fc01e-114">示例</span><span class="sxs-lookup"><span data-stu-id="fc01e-114">Example</span></span>

<span data-ttu-id="fc01e-115">给定一个操作 `op` ，以下两个代码段是等效的：</span><span class="sxs-lookup"><span data-stu-id="fc01e-115">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a><span data-ttu-id="fc01e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc01e-116">See Also</span></span>

- [<span data-ttu-id="fc01e-117">Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="fc01e-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)