---
uid: Microsoft.Quantum.Arrays.Flattened
title: 平展函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848618"
---
# <a name="flattened-function"></a><span data-ttu-id="4b6e7-102">平展函数</span><span class="sxs-lookup"><span data-stu-id="4b6e7-102">Flattened function</span></span>

<span data-ttu-id="4b6e7-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4b6e7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4b6e7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b6e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b6e7-105">给定数组的数组，返回所有数组的串联。</span><span class="sxs-lookup"><span data-stu-id="4b6e7-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4b6e7-106">输入</span><span class="sxs-lookup"><span data-stu-id="4b6e7-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="4b6e7-107">数组： t [] []</span><span class="sxs-lookup"><span data-stu-id="4b6e7-107">arrays : 'T[][]</span></span>

<span data-ttu-id="4b6e7-108">数组的数组。</span><span class="sxs-lookup"><span data-stu-id="4b6e7-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="4b6e7-109">输出： t []</span><span class="sxs-lookup"><span data-stu-id="4b6e7-109">Output : 'T[]</span></span>

<span data-ttu-id="4b6e7-110">所有数组的串联。</span><span class="sxs-lookup"><span data-stu-id="4b6e7-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4b6e7-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="4b6e7-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b6e7-112">找</span><span class="sxs-lookup"><span data-stu-id="4b6e7-112">'T</span></span>

<span data-ttu-id="4b6e7-113">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="4b6e7-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="4b6e7-114">示例</span><span class="sxs-lookup"><span data-stu-id="4b6e7-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```