---
uid: Microsoft.Quantum.Canon.Repeat
title: 重复操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695972"
---
# <a name="repeat-operation"></a><span data-ttu-id="bc663-102">重复操作</span><span class="sxs-lookup"><span data-stu-id="bc663-102">Repeat operation</span></span>

<span data-ttu-id="bc663-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc663-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc663-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc663-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc663-105">在给定的次数后重复操作。</span><span class="sxs-lookup"><span data-stu-id="bc663-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="bc663-106">输入</span><span class="sxs-lookup"><span data-stu-id="bc663-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="bc663-107">op： ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc663-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bc663-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="bc663-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="bc663-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc663-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc663-110">要调用的次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="bc663-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="bc663-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="bc663-111">input : 'TInput</span></span>

<span data-ttu-id="bc663-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="bc663-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc663-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc663-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc663-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="bc663-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="bc663-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="bc663-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="bc663-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc663-116">See Also</span></span>

- [<span data-ttu-id="bc663-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="bc663-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="bc663-118">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="bc663-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="bc663-119">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="bc663-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="bc663-120">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="bc663-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)