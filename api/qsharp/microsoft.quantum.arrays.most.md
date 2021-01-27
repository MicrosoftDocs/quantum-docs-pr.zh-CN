---
uid: Microsoft.Quantum.Arrays.Most
title: 大多数函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845585"
---
# <a name="most-function"></a><span data-ttu-id="27e88-102">大多数函数</span><span class="sxs-lookup"><span data-stu-id="27e88-102">Most function</span></span>

<span data-ttu-id="27e88-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="27e88-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="27e88-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27e88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27e88-105">创建一个等于输入数组的数组，只不过最后一个数组元素被删除。</span><span class="sxs-lookup"><span data-stu-id="27e88-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="27e88-106">输入</span><span class="sxs-lookup"><span data-stu-id="27e88-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="27e88-107">array： t []</span><span class="sxs-lookup"><span data-stu-id="27e88-107">array : 'T[]</span></span>

<span data-ttu-id="27e88-108">一个数组，其第一个到第二个元素是形成输出数组。</span><span class="sxs-lookup"><span data-stu-id="27e88-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="27e88-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="27e88-109">Output : 'T[]</span></span>

<span data-ttu-id="27e88-110">包含元素的数组 `array[0..Length(array) - 2]` 。</span><span class="sxs-lookup"><span data-stu-id="27e88-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="27e88-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="27e88-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27e88-112">找</span><span class="sxs-lookup"><span data-stu-id="27e88-112">'T</span></span>

<span data-ttu-id="27e88-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="27e88-113">The type of the array elements.</span></span>