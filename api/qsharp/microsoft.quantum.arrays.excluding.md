---
uid: Microsoft.Quantum.Arrays.Excluding
title: 排除函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: c117431e3d98bba4ed3d29cb0b171247bf77be0b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848657"
---
# <a name="excluding-function"></a><span data-ttu-id="10797-102">排除函数</span><span class="sxs-lookup"><span data-stu-id="10797-102">Excluding function</span></span>

<span data-ttu-id="10797-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="10797-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="10797-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10797-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10797-105">返回一个数组，其中包含另一个数组的元素，而不包括给定索引列表中的元素。</span><span class="sxs-lookup"><span data-stu-id="10797-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="10797-106">输入</span><span class="sxs-lookup"><span data-stu-id="10797-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="10797-107">删除： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="10797-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="10797-108">指示应从输出中排除哪些元素的索引数组。</span><span class="sxs-lookup"><span data-stu-id="10797-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="10797-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="10797-109">array : 'T[]</span></span>

<span data-ttu-id="10797-110">输出数组中的值采用的数组。</span><span class="sxs-lookup"><span data-stu-id="10797-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="10797-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="10797-111">Output : 'T[]</span></span>

<span data-ttu-id="10797-112">一个数组， `output` 它 `output[0]` 是 `array` 其索引未出现在中的第一个元素 `remove` ，这 `output[1]` 是第二个这样的元素，依此类推。</span><span class="sxs-lookup"><span data-stu-id="10797-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="10797-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="10797-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="10797-114">找</span><span class="sxs-lookup"><span data-stu-id="10797-114">'T</span></span>

<span data-ttu-id="10797-115">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="10797-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="10797-116">示例</span><span class="sxs-lookup"><span data-stu-id="10797-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Excluding([1, 3, 4], array);
```