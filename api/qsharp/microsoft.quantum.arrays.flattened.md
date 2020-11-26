---
uid: Microsoft.Quantum.Arrays.Flattened
title: 平展函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221209"
---
# <a name="flattened-function"></a><span data-ttu-id="0dff1-102">平展函数</span><span class="sxs-lookup"><span data-stu-id="0dff1-102">Flattened function</span></span>

<span data-ttu-id="0dff1-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0dff1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0dff1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0dff1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0dff1-105">给定数组的数组，返回所有数组的串联。</span><span class="sxs-lookup"><span data-stu-id="0dff1-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0dff1-106">输入</span><span class="sxs-lookup"><span data-stu-id="0dff1-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="0dff1-107">数组： t [] []</span><span class="sxs-lookup"><span data-stu-id="0dff1-107">arrays : 'T[][]</span></span>

<span data-ttu-id="0dff1-108">数组的数组。</span><span class="sxs-lookup"><span data-stu-id="0dff1-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="0dff1-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="0dff1-109">Output : 'T[]</span></span>

<span data-ttu-id="0dff1-110">所有数组的串联。</span><span class="sxs-lookup"><span data-stu-id="0dff1-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0dff1-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="0dff1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0dff1-112">找</span><span class="sxs-lookup"><span data-stu-id="0dff1-112">'T</span></span>

<span data-ttu-id="0dff1-113">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="0dff1-113">The type of `array` elements.</span></span>