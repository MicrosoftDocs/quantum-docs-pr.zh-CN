---
uid: Microsoft.Quantum.Arrays.Merged
title: 合并函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845607"
---
# <a name="merged-function"></a><span data-ttu-id="10f52-102">合并函数</span><span class="sxs-lookup"><span data-stu-id="10f52-102">Merged function</span></span>

<span data-ttu-id="10f52-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="10f52-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="10f52-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10f52-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10f52-105">给定两个已排序的数组，返回一个数组，其中包含按排序顺序排列的元素。</span><span class="sxs-lookup"><span data-stu-id="10f52-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="10f52-106">由合并排序在内部使用。</span><span class="sxs-lookup"><span data-stu-id="10f52-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="10f52-107">输入</span><span class="sxs-lookup"><span data-stu-id="10f52-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="10f52-108">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="10f52-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="10f52-109">left： t []</span><span class="sxs-lookup"><span data-stu-id="10f52-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="10f52-110">right： t []</span><span class="sxs-lookup"><span data-stu-id="10f52-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="10f52-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="10f52-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="10f52-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="10f52-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="10f52-113">找</span><span class="sxs-lookup"><span data-stu-id="10f52-113">'T</span></span>

