---
uid: Microsoft.Quantum.Arrays.Padded
title: 填充的函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696474"
---
# <a name="padded-function"></a><span data-ttu-id="bbe69-102">填充的函数</span><span class="sxs-lookup"><span data-stu-id="bbe69-102">Padded function</span></span>

<span data-ttu-id="bbe69-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bbe69-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bbe69-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbe69-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbe69-105">返回使用指定的值（最大指定长度）填充的数组。</span><span class="sxs-lookup"><span data-stu-id="bbe69-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bbe69-106">输入</span><span class="sxs-lookup"><span data-stu-id="bbe69-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="bbe69-107">nElementsTotal： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bbe69-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bbe69-108">填充的数组的长度。</span><span class="sxs-lookup"><span data-stu-id="bbe69-108">The length of the padded array.</span></span> <span data-ttu-id="bbe69-109">如果为正， `inputArray` 则在头中填充。</span><span class="sxs-lookup"><span data-stu-id="bbe69-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="bbe69-110">如果此为负， `inputArray` 则在结尾处填充。</span><span class="sxs-lookup"><span data-stu-id="bbe69-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="bbe69-111">defaultElement： t</span><span class="sxs-lookup"><span data-stu-id="bbe69-111">defaultElement : 'T</span></span>

<span data-ttu-id="bbe69-112">用于填充元素的默认值。</span><span class="sxs-lookup"><span data-stu-id="bbe69-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="bbe69-113">inputArray： t []</span><span class="sxs-lookup"><span data-stu-id="bbe69-113">inputArray : 'T[]</span></span>

<span data-ttu-id="bbe69-114">其值位于输出数组的开头的数组。</span><span class="sxs-lookup"><span data-stu-id="bbe69-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="bbe69-115">输出： t []</span><span class="sxs-lookup"><span data-stu-id="bbe69-115">Output : 'T[]</span></span>

<span data-ttu-id="bbe69-116">一个数组 `output` ，它是 `inputArray` 在头中填充的， `defaultElement` 直到 `output` 长度为 `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="bbe69-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bbe69-117">类型参数</span><span class="sxs-lookup"><span data-stu-id="bbe69-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbe69-118">找</span><span class="sxs-lookup"><span data-stu-id="bbe69-118">'T</span></span>

<span data-ttu-id="bbe69-119">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="bbe69-119">The type of the array elements.</span></span>