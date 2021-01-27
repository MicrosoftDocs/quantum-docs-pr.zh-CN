---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解压缩函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845371"
---
# <a name="unzipped-function"></a><span data-ttu-id="e6f17-102">解压缩函数</span><span class="sxs-lookup"><span data-stu-id="e6f17-102">Unzipped function</span></span>

<span data-ttu-id="e6f17-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e6f17-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e6f17-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6f17-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6f17-105">给定一个2元组数组，返回两个数组的元组，其中每个数组包含输入数组的元组的元素。</span><span class="sxs-lookup"><span data-stu-id="e6f17-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="e6f17-106">输入</span><span class="sxs-lookup"><span data-stu-id="e6f17-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="e6f17-107">arr： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="e6f17-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="e6f17-108">包含2元组的数组</span><span class="sxs-lookup"><span data-stu-id="e6f17-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="e6f17-109">Output： ( t []，' U [] ) </span><span class="sxs-lookup"><span data-stu-id="e6f17-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="e6f17-110">两个数组，第一个数组包含输入元组的所有第一个元素，第二个数组包含输入元组的所有第二个元素。</span><span class="sxs-lookup"><span data-stu-id="e6f17-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e6f17-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="e6f17-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6f17-112">找</span><span class="sxs-lookup"><span data-stu-id="e6f17-112">'T</span></span>

<span data-ttu-id="e6f17-113">每个元组中第一个元素的类型</span><span class="sxs-lookup"><span data-stu-id="e6f17-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="e6f17-114">' U</span><span class="sxs-lookup"><span data-stu-id="e6f17-114">'U</span></span>

<span data-ttu-id="e6f17-115">每个元组中第二个元素的类型</span><span class="sxs-lookup"><span data-stu-id="e6f17-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="e6f17-116">示例</span><span class="sxs-lookup"><span data-stu-id="e6f17-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="e6f17-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6f17-117">See Also</span></span>

- [<span data-ttu-id="e6f17-118">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="e6f17-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)