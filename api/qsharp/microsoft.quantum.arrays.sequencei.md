---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696460"
---
# <a name="sequencei-function"></a><span data-ttu-id="324b4-102">SequenceI 函数</span><span class="sxs-lookup"><span data-stu-id="324b4-102">SequenceI function</span></span>

<span data-ttu-id="324b4-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="324b4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="324b4-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="324b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="324b4-105">获取给定时间间隔内的整数数组。</span><span class="sxs-lookup"><span data-stu-id="324b4-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="324b4-106">输入</span><span class="sxs-lookup"><span data-stu-id="324b4-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="324b4-107">起始： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="324b4-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="324b4-108">间隔的包含开始索引。</span><span class="sxs-lookup"><span data-stu-id="324b4-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="324b4-109">to： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="324b4-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="324b4-110">不小于的间隔的非独占结束索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="324b4-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="324b4-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="324b4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="324b4-112">一个包含数字序列的数组， `from` `from + 1` ，...， `to` 。</span><span class="sxs-lookup"><span data-stu-id="324b4-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>