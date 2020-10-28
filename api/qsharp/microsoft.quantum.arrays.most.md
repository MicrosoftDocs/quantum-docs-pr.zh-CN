---
uid: Microsoft.Quantum.Arrays.Most
title: 大多数函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696477"
---
# <a name="most-function"></a><span data-ttu-id="1ecf7-102">大多数函数</span><span class="sxs-lookup"><span data-stu-id="1ecf7-102">Most function</span></span>

<span data-ttu-id="1ecf7-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1ecf7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ecf7-105">创建一个等于输入数组的数组，只不过最后一个数组元素被删除。</span><span class="sxs-lookup"><span data-stu-id="1ecf7-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1ecf7-106">输入</span><span class="sxs-lookup"><span data-stu-id="1ecf7-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="1ecf7-107">array： t []</span><span class="sxs-lookup"><span data-stu-id="1ecf7-107">array : 'T[]</span></span>

<span data-ttu-id="1ecf7-108">一个数组，其第一个到第二个元素是形成输出数组。</span><span class="sxs-lookup"><span data-stu-id="1ecf7-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="1ecf7-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="1ecf7-109">Output : 'T[]</span></span>

<span data-ttu-id="1ecf7-110">包含元素的数组 `array[0..Length(array) - 2]` 。</span><span class="sxs-lookup"><span data-stu-id="1ecf7-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1ecf7-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="1ecf7-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1ecf7-112">找</span><span class="sxs-lookup"><span data-stu-id="1ecf7-112">'T</span></span>

<span data-ttu-id="1ecf7-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="1ecf7-113">The type of the array elements.</span></span>