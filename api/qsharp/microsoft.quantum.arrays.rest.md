---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696463"
---
# <a name="rest-function"></a><span data-ttu-id="6f782-102">Rest 函数</span><span class="sxs-lookup"><span data-stu-id="6f782-102">Rest function</span></span>

<span data-ttu-id="6f782-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6f782-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6f782-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f782-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f782-105">创建一个等于输入数组的数组，但第一个数组元素被删除。</span><span class="sxs-lookup"><span data-stu-id="6f782-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="6f782-106">输入</span><span class="sxs-lookup"><span data-stu-id="6f782-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="6f782-107">array： t []</span><span class="sxs-lookup"><span data-stu-id="6f782-107">array : 'T[]</span></span>

<span data-ttu-id="6f782-108">一个数组，其第二个元素是要形成输出数组的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="6f782-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="6f782-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="6f782-109">Output : 'T[]</span></span>

<span data-ttu-id="6f782-110">包含元素的数组 `array[1..Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="6f782-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6f782-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="6f782-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f782-112">找</span><span class="sxs-lookup"><span data-stu-id="6f782-112">'T</span></span>

<span data-ttu-id="6f782-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="6f782-113">The type of the array elements.</span></span>