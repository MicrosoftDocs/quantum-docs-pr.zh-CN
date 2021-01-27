---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 前缀函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845513"
---
# <a name="prefixes-function"></a><span data-ttu-id="bed45-102">前缀函数</span><span class="sxs-lookup"><span data-stu-id="bed45-102">Prefixes function</span></span>

<span data-ttu-id="bed45-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bed45-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bed45-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bed45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bed45-105">给定一个数组，返回其所有前缀。</span><span class="sxs-lookup"><span data-stu-id="bed45-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="bed45-106">说明</span><span class="sxs-lookup"><span data-stu-id="bed45-106">Description</span></span>

<span data-ttu-id="bed45-107">返回一个数组，其中包含所有前缀（从仅具有第一个元素直到整个数组的数组开始）。</span><span class="sxs-lookup"><span data-stu-id="bed45-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="bed45-108">输入</span><span class="sxs-lookup"><span data-stu-id="bed45-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bed45-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="bed45-109">array : 'T[]</span></span>

<span data-ttu-id="bed45-110">元素的数组。</span><span class="sxs-lookup"><span data-stu-id="bed45-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="bed45-111">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="bed45-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bed45-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="bed45-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bed45-113">找</span><span class="sxs-lookup"><span data-stu-id="bed45-113">'T</span></span>

<span data-ttu-id="bed45-114">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="bed45-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="bed45-115">示例</span><span class="sxs-lookup"><span data-stu-id="bed45-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```