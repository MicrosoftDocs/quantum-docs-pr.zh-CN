---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846205"
---
# <a name="drawmany-operation"></a><span data-ttu-id="39955-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="39955-102">DrawMany operation</span></span>

<span data-ttu-id="39955-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39955-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39955-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39955-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39955-105">对给定数量的样本重复操作，并在数组中收集其输出。</span><span class="sxs-lookup"><span data-stu-id="39955-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="39955-106">输入</span><span class="sxs-lookup"><span data-stu-id="39955-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="39955-107">op： ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="39955-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="39955-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="39955-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="39955-109">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39955-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39955-110">要收集的调用的示例数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="39955-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="39955-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="39955-111">input : 'TInput</span></span>

<span data-ttu-id="39955-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="39955-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="39955-113">输出： "TOutput []</span><span class="sxs-lookup"><span data-stu-id="39955-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="39955-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="39955-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="39955-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="39955-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="39955-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="39955-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="39955-117">示例</span><span class="sxs-lookup"><span data-stu-id="39955-117">Example</span></span>

<span data-ttu-id="39955-118">下面的示例为一个整数，给定一个操作，该操作一次采样一个位。</span><span class="sxs-lookup"><span data-stu-id="39955-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="39955-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39955-119">See Also</span></span>

- [<span data-ttu-id="39955-120">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="39955-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)