---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205433"
---
# <a name="repeatc-operation"></a><span data-ttu-id="cb30a-102">RepeatC 操作</span><span class="sxs-lookup"><span data-stu-id="cb30a-102">RepeatC operation</span></span>

<span data-ttu-id="cb30a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb30a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb30a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb30a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb30a-105">在给定的次数后重复操作。</span><span class="sxs-lookup"><span data-stu-id="cb30a-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="cb30a-106">输入</span><span class="sxs-lookup"><span data-stu-id="cb30a-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="cb30a-107">op： ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="cb30a-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="cb30a-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="cb30a-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="cb30a-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb30a-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb30a-110">要调用的次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="cb30a-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="cb30a-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="cb30a-111">input : 'TInput</span></span>

<span data-ttu-id="cb30a-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="cb30a-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb30a-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb30a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cb30a-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="cb30a-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="cb30a-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="cb30a-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="cb30a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb30a-116">See Also</span></span>

- [<span data-ttu-id="cb30a-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="cb30a-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="cb30a-118">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="cb30a-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="cb30a-119">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="cb30a-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="cb30a-120">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="cb30a-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)