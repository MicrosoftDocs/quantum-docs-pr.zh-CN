---
uid: Microsoft.Quantum.Arrays.Merged
title: 合并函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220631"
---
# <a name="merged-function"></a><span data-ttu-id="b8a15-102">合并函数</span><span class="sxs-lookup"><span data-stu-id="b8a15-102">Merged function</span></span>

<span data-ttu-id="b8a15-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b8a15-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b8a15-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8a15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8a15-105">给定两个已排序的数组，返回一个数组，其中包含按排序顺序排列的元素。</span><span class="sxs-lookup"><span data-stu-id="b8a15-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="b8a15-106">由合并排序在内部使用。</span><span class="sxs-lookup"><span data-stu-id="b8a15-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b8a15-107">输入</span><span class="sxs-lookup"><span data-stu-id="b8a15-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="b8a15-108">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b8a15-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="b8a15-109">left： t []</span><span class="sxs-lookup"><span data-stu-id="b8a15-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="b8a15-110">right： t []</span><span class="sxs-lookup"><span data-stu-id="b8a15-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="b8a15-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="b8a15-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b8a15-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="b8a15-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b8a15-113">找</span><span class="sxs-lookup"><span data-stu-id="b8a15-113">'T</span></span>

