---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反转函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696462"
---
# <a name="reversed-function"></a><span data-ttu-id="96a4b-102">反转函数</span><span class="sxs-lookup"><span data-stu-id="96a4b-102">Reversed function</span></span>

<span data-ttu-id="96a4b-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="96a4b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="96a4b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96a4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96a4b-105">创建一个数组，该数组包含与输入数组相同的元素，但其顺序相反。</span><span class="sxs-lookup"><span data-stu-id="96a4b-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="96a4b-106">输入</span><span class="sxs-lookup"><span data-stu-id="96a4b-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="96a4b-107">array： t []</span><span class="sxs-lookup"><span data-stu-id="96a4b-107">array : 'T[]</span></span>

<span data-ttu-id="96a4b-108">要以相反顺序复制其元素的数组。</span><span class="sxs-lookup"><span data-stu-id="96a4b-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="96a4b-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="96a4b-109">Output : 'T[]</span></span>

<span data-ttu-id="96a4b-110">包含元素的数组 `array[Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="96a4b-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="96a4b-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="96a4b-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="96a4b-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="96a4b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96a4b-113">找</span><span class="sxs-lookup"><span data-stu-id="96a4b-113">'T</span></span>

<span data-ttu-id="96a4b-114">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="96a4b-114">The type of the array elements.</span></span>