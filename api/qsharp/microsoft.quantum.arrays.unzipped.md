---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解压缩函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696442"
---
# <a name="unzipped-function"></a><span data-ttu-id="8c602-102">解压缩函数</span><span class="sxs-lookup"><span data-stu-id="8c602-102">Unzipped function</span></span>

<span data-ttu-id="8c602-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8c602-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8c602-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c602-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c602-105">给定一个2元组数组，返回两个数组的元组，其中每个数组包含输入数组的元组的元素。</span><span class="sxs-lookup"><span data-stu-id="8c602-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="8c602-106">输入</span><span class="sxs-lookup"><span data-stu-id="8c602-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="8c602-107">arr： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="8c602-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="8c602-108">包含2元组的数组</span><span class="sxs-lookup"><span data-stu-id="8c602-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="8c602-109">Output： ( t []，' U [] ) </span><span class="sxs-lookup"><span data-stu-id="8c602-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="8c602-110">两个数组，第一个数组包含输入元组的所有第一个元素，第二个数组包含输入元组的所有第二个元素。</span><span class="sxs-lookup"><span data-stu-id="8c602-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8c602-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="8c602-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8c602-112">找</span><span class="sxs-lookup"><span data-stu-id="8c602-112">'T</span></span>

<span data-ttu-id="8c602-113">每个元组中第一个元素的类型</span><span class="sxs-lookup"><span data-stu-id="8c602-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="8c602-114">' U</span><span class="sxs-lookup"><span data-stu-id="8c602-114">'U</span></span>

<span data-ttu-id="8c602-115">每个元组中第二个元素的类型</span><span class="sxs-lookup"><span data-stu-id="8c602-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="8c602-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c602-116">See Also</span></span>

- [<span data-ttu-id="8c602-117">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="8c602-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)