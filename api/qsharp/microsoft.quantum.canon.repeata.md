---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205550"
---
# <a name="repeata-operation"></a><span data-ttu-id="72451-102">RepeatA 操作</span><span class="sxs-lookup"><span data-stu-id="72451-102">RepeatA operation</span></span>

<span data-ttu-id="72451-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72451-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72451-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72451-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72451-105">在给定的次数后重复操作。</span><span class="sxs-lookup"><span data-stu-id="72451-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="72451-106">输入</span><span class="sxs-lookup"><span data-stu-id="72451-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="72451-107">op： ' TInput => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="72451-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="72451-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="72451-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="72451-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72451-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72451-110">要调用的次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="72451-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="72451-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="72451-111">input : 'TInput</span></span>

<span data-ttu-id="72451-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="72451-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72451-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72451-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72451-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="72451-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="72451-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="72451-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="72451-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72451-116">See Also</span></span>

- [<span data-ttu-id="72451-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="72451-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="72451-118">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="72451-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="72451-119">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="72451-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="72451-120">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="72451-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)