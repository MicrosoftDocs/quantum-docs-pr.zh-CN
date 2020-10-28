---
uid: Microsoft.Quantum.Arrays.Chunks
title: 区块函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696555"
---
# <a name="chunks-function"></a><span data-ttu-id="3aaaf-102">区块函数</span><span class="sxs-lookup"><span data-stu-id="3aaaf-102">Chunks function</span></span>

<span data-ttu-id="3aaaf-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3aaaf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3aaaf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3aaaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3aaaf-105">将数组拆分为长度相等的多个部分。</span><span class="sxs-lookup"><span data-stu-id="3aaaf-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="3aaaf-106">输入</span><span class="sxs-lookup"><span data-stu-id="3aaaf-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="3aaaf-107">nElements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3aaaf-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3aaaf-108">每个区块的长度。</span><span class="sxs-lookup"><span data-stu-id="3aaaf-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="3aaaf-109">arr： t []</span><span class="sxs-lookup"><span data-stu-id="3aaaf-109">arr : 'T[]</span></span>

<span data-ttu-id="3aaaf-110">要拆分的数组。</span><span class="sxs-lookup"><span data-stu-id="3aaaf-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="3aaaf-111">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="3aaaf-111">Output : 'T[][]</span></span>

<span data-ttu-id="3aaaf-112">包含原始数组的每个块的数组。</span><span class="sxs-lookup"><span data-stu-id="3aaaf-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3aaaf-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="3aaaf-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3aaaf-114">找</span><span class="sxs-lookup"><span data-stu-id="3aaaf-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3aaaf-115">注解</span><span class="sxs-lookup"><span data-stu-id="3aaaf-115">Remarks</span></span>

<span data-ttu-id="3aaaf-116">请注意，输出的最后一个元素可能比不能被整除的更短 `nElements` `Length(arr)` `nElements` 。</span><span class="sxs-lookup"><span data-stu-id="3aaaf-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>