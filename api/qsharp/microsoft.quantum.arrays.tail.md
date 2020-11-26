---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220087"
---
# <a name="tail-function"></a><span data-ttu-id="51385-102">Tail 函数</span><span class="sxs-lookup"><span data-stu-id="51385-102">Tail function</span></span>

<span data-ttu-id="51385-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="51385-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="51385-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51385-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51385-105">返回数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="51385-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="51385-106">输入</span><span class="sxs-lookup"><span data-stu-id="51385-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="51385-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="51385-107">array : 'A[]</span></span>

<span data-ttu-id="51385-108">要获取其最后一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="51385-108">Array of which the last element is taken.</span></span> <span data-ttu-id="51385-109">数组的长度必须至少为1。</span><span class="sxs-lookup"><span data-stu-id="51385-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="51385-110">输出： "A</span><span class="sxs-lookup"><span data-stu-id="51385-110">Output : 'A</span></span>

<span data-ttu-id="51385-111">数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="51385-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="51385-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="51385-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="51385-113">' A</span><span class="sxs-lookup"><span data-stu-id="51385-113">'A</span></span>

<span data-ttu-id="51385-114">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="51385-114">The type of the array elements.</span></span>