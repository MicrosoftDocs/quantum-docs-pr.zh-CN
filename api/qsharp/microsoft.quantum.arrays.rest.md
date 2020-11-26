---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220378"
---
# <a name="rest-function"></a><span data-ttu-id="23cf8-102">Rest 函数</span><span class="sxs-lookup"><span data-stu-id="23cf8-102">Rest function</span></span>

<span data-ttu-id="23cf8-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="23cf8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="23cf8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23cf8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23cf8-105">创建一个等于输入数组的数组，但第一个数组元素被删除。</span><span class="sxs-lookup"><span data-stu-id="23cf8-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="23cf8-106">输入</span><span class="sxs-lookup"><span data-stu-id="23cf8-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="23cf8-107">array： t []</span><span class="sxs-lookup"><span data-stu-id="23cf8-107">array : 'T[]</span></span>

<span data-ttu-id="23cf8-108">一个数组，其第二个元素是要形成输出数组的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="23cf8-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="23cf8-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="23cf8-109">Output : 'T[]</span></span>

<span data-ttu-id="23cf8-110">包含元素的数组 `array[1..Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="23cf8-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="23cf8-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="23cf8-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23cf8-112">找</span><span class="sxs-lookup"><span data-stu-id="23cf8-112">'T</span></span>

<span data-ttu-id="23cf8-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="23cf8-113">The type of the array elements.</span></span>