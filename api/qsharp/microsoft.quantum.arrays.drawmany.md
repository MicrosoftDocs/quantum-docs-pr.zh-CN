---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209989"
---
# <a name="drawmany-operation"></a><span data-ttu-id="83d98-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="83d98-102">DrawMany operation</span></span>

<span data-ttu-id="83d98-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="83d98-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="83d98-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83d98-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83d98-105">对给定数量的样本重复操作，并在数组中收集其输出。</span><span class="sxs-lookup"><span data-stu-id="83d98-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="83d98-106">输入</span><span class="sxs-lookup"><span data-stu-id="83d98-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="83d98-107">op： ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="83d98-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="83d98-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="83d98-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="83d98-109">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83d98-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83d98-110">要收集的调用的示例数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="83d98-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="83d98-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="83d98-111">input : 'TInput</span></span>

<span data-ttu-id="83d98-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="83d98-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="83d98-113">输出： "TOutput []</span><span class="sxs-lookup"><span data-stu-id="83d98-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="83d98-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="83d98-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="83d98-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="83d98-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="83d98-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="83d98-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="83d98-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83d98-117">See Also</span></span>

- [<span data-ttu-id="83d98-118">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="83d98-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)