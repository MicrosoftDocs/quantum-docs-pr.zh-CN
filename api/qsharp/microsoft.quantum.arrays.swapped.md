---
uid: Microsoft.Quantum.Arrays.Swapped
title: 交换函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696448"
---
# <a name="swapped-function"></a><span data-ttu-id="82603-102">交换函数</span><span class="sxs-lookup"><span data-stu-id="82603-102">Swapped function</span></span>

<span data-ttu-id="82603-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="82603-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="82603-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82603-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82603-105">应用数组中两个元素的交换。</span><span class="sxs-lookup"><span data-stu-id="82603-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="82603-106">输入</span><span class="sxs-lookup"><span data-stu-id="82603-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="82603-107">firstIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82603-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82603-108">要交换的第一个元素的索引。</span><span class="sxs-lookup"><span data-stu-id="82603-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="82603-109">secondIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82603-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82603-110">要交换的第二个元素的索引。</span><span class="sxs-lookup"><span data-stu-id="82603-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="82603-111">arr： t []</span><span class="sxs-lookup"><span data-stu-id="82603-111">arr : 'T[]</span></span>

<span data-ttu-id="82603-112">包含要交换的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="82603-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="82603-113">输出： t []</span><span class="sxs-lookup"><span data-stu-id="82603-113">Output : 'T[]</span></span>

<span data-ttu-id="82603-114">应用了就地交换的数组。</span><span class="sxs-lookup"><span data-stu-id="82603-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="82603-115">示例</span><span class="sxs-lookup"><span data-stu-id="82603-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="82603-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="82603-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="82603-117">找</span><span class="sxs-lookup"><span data-stu-id="82603-117">'T</span></span>

