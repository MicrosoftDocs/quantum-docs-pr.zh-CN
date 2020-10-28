---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696035"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="0e56a-102">IterateThroughCartesianProduct 操作</span><span class="sxs-lookup"><span data-stu-id="0e56a-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="0e56a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e56a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e56a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e56a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e56a-105">对若干范围内笛卡尔积中的每个索引应用操作。</span><span class="sxs-lookup"><span data-stu-id="0e56a-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="0e56a-106">说明</span><span class="sxs-lookup"><span data-stu-id="0e56a-106">Description</span></span>

<span data-ttu-id="0e56a-107">以迭代方式为、、... 的笛卡尔积的每个元素应用操作 `0..(bounds[0] - 1)` `0..(bounds[1] - 1)``0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="0e56a-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="0e56a-108">输入</span><span class="sxs-lookup"><span data-stu-id="0e56a-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="0e56a-109">界限： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0e56a-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0e56a-110">指定要循环访问的范围的数组，其中每个范围都指定为整数长度。</span><span class="sxs-lookup"><span data-stu-id="0e56a-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="0e56a-111">op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e56a-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0e56a-112">为给定笛卡尔积的每个元素调用的操作。</span><span class="sxs-lookup"><span data-stu-id="0e56a-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e56a-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e56a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0e56a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e56a-114">See Also</span></span>

- [<span data-ttu-id="0e56a-115">Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="0e56a-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)