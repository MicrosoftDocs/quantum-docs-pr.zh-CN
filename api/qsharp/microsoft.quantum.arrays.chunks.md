---
uid: Microsoft.Quantum.Arrays.Chunks
title: 区块函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842872"
---
# <a name="chunks-function"></a><span data-ttu-id="16b58-102">区块函数</span><span class="sxs-lookup"><span data-stu-id="16b58-102">Chunks function</span></span>

<span data-ttu-id="16b58-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="16b58-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="16b58-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16b58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16b58-105">将数组拆分为长度相等的多个部分。</span><span class="sxs-lookup"><span data-stu-id="16b58-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="16b58-106">输入</span><span class="sxs-lookup"><span data-stu-id="16b58-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="16b58-107">nElements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="16b58-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="16b58-108">每个区块的长度。</span><span class="sxs-lookup"><span data-stu-id="16b58-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="16b58-109">arr： t []</span><span class="sxs-lookup"><span data-stu-id="16b58-109">arr : 'T[]</span></span>

<span data-ttu-id="16b58-110">要拆分的数组。</span><span class="sxs-lookup"><span data-stu-id="16b58-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="16b58-111">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="16b58-111">Output : 'T[][]</span></span>

<span data-ttu-id="16b58-112">包含原始数组的每个块的数组。</span><span class="sxs-lookup"><span data-stu-id="16b58-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="16b58-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="16b58-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16b58-114">找</span><span class="sxs-lookup"><span data-stu-id="16b58-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="16b58-115">备注</span><span class="sxs-lookup"><span data-stu-id="16b58-115">Remarks</span></span>

<span data-ttu-id="16b58-116">请注意，输出的最后一个元素可能比不能被整除的更短 `nElements` `Length(arr)` `nElements` 。</span><span class="sxs-lookup"><span data-stu-id="16b58-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>