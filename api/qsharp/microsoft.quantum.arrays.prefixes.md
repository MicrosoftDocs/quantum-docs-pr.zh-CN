---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 前缀函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696467"
---
# <a name="prefixes-function"></a><span data-ttu-id="0c974-102">前缀函数</span><span class="sxs-lookup"><span data-stu-id="0c974-102">Prefixes function</span></span>

<span data-ttu-id="0c974-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0c974-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0c974-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c974-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c974-105">给定一个数组，返回其所有前缀。</span><span class="sxs-lookup"><span data-stu-id="0c974-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="0c974-106">说明</span><span class="sxs-lookup"><span data-stu-id="0c974-106">Description</span></span>

<span data-ttu-id="0c974-107">返回一个数组，其中包含所有前缀（从仅具有第一个元素直到整个数组的数组开始）。</span><span class="sxs-lookup"><span data-stu-id="0c974-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="0c974-108">输入</span><span class="sxs-lookup"><span data-stu-id="0c974-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="0c974-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="0c974-109">array : 'T[]</span></span>

<span data-ttu-id="0c974-110">元素的数组。</span><span class="sxs-lookup"><span data-stu-id="0c974-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="0c974-111">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="0c974-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0c974-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="0c974-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0c974-113">找</span><span class="sxs-lookup"><span data-stu-id="0c974-113">'T</span></span>

<span data-ttu-id="0c974-114">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="0c974-114">The type of `array` elements.</span></span>