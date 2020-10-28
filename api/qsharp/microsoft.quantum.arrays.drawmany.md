---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696539"
---
# <a name="drawmany-operation"></a><span data-ttu-id="f1689-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="f1689-102">DrawMany operation</span></span>

<span data-ttu-id="f1689-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f1689-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f1689-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1689-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1689-105">对给定数量的样本重复操作，并在数组中收集其输出。</span><span class="sxs-lookup"><span data-stu-id="f1689-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="f1689-106">输入</span><span class="sxs-lookup"><span data-stu-id="f1689-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="f1689-107">op： ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="f1689-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="f1689-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="f1689-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="f1689-109">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1689-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1689-110">要收集的调用的示例数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f1689-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f1689-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="f1689-111">input : 'TInput</span></span>

<span data-ttu-id="f1689-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f1689-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="f1689-113">输出： "TOutput []</span><span class="sxs-lookup"><span data-stu-id="f1689-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f1689-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="f1689-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f1689-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="f1689-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="f1689-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="f1689-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="f1689-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1689-117">See Also</span></span>

- [<span data-ttu-id="f1689-118">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="f1689-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)