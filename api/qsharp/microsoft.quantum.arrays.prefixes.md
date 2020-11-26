---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 前缀函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220377"
---
# <a name="prefixes-function"></a><span data-ttu-id="af409-102">前缀函数</span><span class="sxs-lookup"><span data-stu-id="af409-102">Prefixes function</span></span>

<span data-ttu-id="af409-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="af409-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="af409-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af409-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af409-105">给定一个数组，返回其所有前缀。</span><span class="sxs-lookup"><span data-stu-id="af409-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="af409-106">描述</span><span class="sxs-lookup"><span data-stu-id="af409-106">Description</span></span>

<span data-ttu-id="af409-107">返回一个数组，其中包含所有前缀（从仅具有第一个元素直到整个数组的数组开始）。</span><span class="sxs-lookup"><span data-stu-id="af409-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="af409-108">输入</span><span class="sxs-lookup"><span data-stu-id="af409-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="af409-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="af409-109">array : 'T[]</span></span>

<span data-ttu-id="af409-110">元素的数组。</span><span class="sxs-lookup"><span data-stu-id="af409-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="af409-111">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="af409-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="af409-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="af409-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af409-113">找</span><span class="sxs-lookup"><span data-stu-id="af409-113">'T</span></span>

<span data-ttu-id="af409-114">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="af409-114">The type of `array` elements.</span></span>