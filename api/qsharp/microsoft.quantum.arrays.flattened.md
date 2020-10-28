---
uid: Microsoft.Quantum.Arrays.Flattened
title: 平展函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696517"
---
# <a name="flattened-function"></a><span data-ttu-id="d99a2-102">平展函数</span><span class="sxs-lookup"><span data-stu-id="d99a2-102">Flattened function</span></span>

<span data-ttu-id="d99a2-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d99a2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d99a2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d99a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d99a2-105">给定数组的数组，返回所有数组的串联。</span><span class="sxs-lookup"><span data-stu-id="d99a2-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d99a2-106">输入</span><span class="sxs-lookup"><span data-stu-id="d99a2-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="d99a2-107">数组： t [] []</span><span class="sxs-lookup"><span data-stu-id="d99a2-107">arrays : 'T[][]</span></span>

<span data-ttu-id="d99a2-108">数组的数组。</span><span class="sxs-lookup"><span data-stu-id="d99a2-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="d99a2-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="d99a2-109">Output : 'T[]</span></span>

<span data-ttu-id="d99a2-110">所有数组的串联。</span><span class="sxs-lookup"><span data-stu-id="d99a2-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d99a2-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="d99a2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d99a2-112">找</span><span class="sxs-lookup"><span data-stu-id="d99a2-112">'T</span></span>

<span data-ttu-id="d99a2-113">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="d99a2-113">The type of `array` elements.</span></span>