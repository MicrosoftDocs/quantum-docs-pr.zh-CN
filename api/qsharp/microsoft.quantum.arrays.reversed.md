---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反转函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845455"
---
# <a name="reversed-function"></a><span data-ttu-id="5153e-102">反转函数</span><span class="sxs-lookup"><span data-stu-id="5153e-102">Reversed function</span></span>

<span data-ttu-id="5153e-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5153e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5153e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5153e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5153e-105">创建一个数组，该数组包含与输入数组相同的元素，但其顺序相反。</span><span class="sxs-lookup"><span data-stu-id="5153e-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5153e-106">输入</span><span class="sxs-lookup"><span data-stu-id="5153e-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="5153e-107">array： t []</span><span class="sxs-lookup"><span data-stu-id="5153e-107">array : 'T[]</span></span>

<span data-ttu-id="5153e-108">要以相反顺序复制其元素的数组。</span><span class="sxs-lookup"><span data-stu-id="5153e-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="5153e-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="5153e-109">Output : 'T[]</span></span>

<span data-ttu-id="5153e-110">包含元素的数组 `array[Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="5153e-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="5153e-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="5153e-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5153e-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="5153e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5153e-113">找</span><span class="sxs-lookup"><span data-stu-id="5153e-113">'T</span></span>

<span data-ttu-id="5153e-114">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5153e-114">The type of the array elements.</span></span>