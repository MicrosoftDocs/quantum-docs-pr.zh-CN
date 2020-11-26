---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解压缩函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219951"
---
# <a name="unzipped-function"></a><span data-ttu-id="43459-102">解压缩函数</span><span class="sxs-lookup"><span data-stu-id="43459-102">Unzipped function</span></span>

<span data-ttu-id="43459-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="43459-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="43459-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43459-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43459-105">给定一个2元组数组，返回两个数组的元组，其中每个数组包含输入数组的元组的元素。</span><span class="sxs-lookup"><span data-stu-id="43459-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="43459-106">输入</span><span class="sxs-lookup"><span data-stu-id="43459-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="43459-107">arr： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="43459-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="43459-108">包含2元组的数组</span><span class="sxs-lookup"><span data-stu-id="43459-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="43459-109">Output： ( t []，' U [] ) </span><span class="sxs-lookup"><span data-stu-id="43459-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="43459-110">两个数组，第一个数组包含输入元组的所有第一个元素，第二个数组包含输入元组的所有第二个元素。</span><span class="sxs-lookup"><span data-stu-id="43459-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="43459-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="43459-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43459-112">找</span><span class="sxs-lookup"><span data-stu-id="43459-112">'T</span></span>

<span data-ttu-id="43459-113">每个元组中第一个元素的类型</span><span class="sxs-lookup"><span data-stu-id="43459-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="43459-114">' U</span><span class="sxs-lookup"><span data-stu-id="43459-114">'U</span></span>

<span data-ttu-id="43459-115">每个元组中第二个元素的类型</span><span class="sxs-lookup"><span data-stu-id="43459-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="43459-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43459-116">See Also</span></span>

- [<span data-ttu-id="43459-117">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="43459-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)