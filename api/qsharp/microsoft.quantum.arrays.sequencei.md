---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220291"
---
# <a name="sequencei-function"></a><span data-ttu-id="b548c-102">SequenceI 函数</span><span class="sxs-lookup"><span data-stu-id="b548c-102">SequenceI function</span></span>

<span data-ttu-id="b548c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b548c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b548c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b548c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b548c-105">获取给定时间间隔内的整数数组。</span><span class="sxs-lookup"><span data-stu-id="b548c-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="b548c-106">输入</span><span class="sxs-lookup"><span data-stu-id="b548c-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="b548c-107">起始： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b548c-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b548c-108">间隔的包含开始索引。</span><span class="sxs-lookup"><span data-stu-id="b548c-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="b548c-109">to： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b548c-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b548c-110">不小于的间隔的非独占结束索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="b548c-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="b548c-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b548c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b548c-112">一个包含数字序列的数组， `from` `from + 1` ，...， `to` 。</span><span class="sxs-lookup"><span data-stu-id="b548c-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>