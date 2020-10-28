---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 8dc178374bdc9f8bf9f8aed57b9ae9a56995dec6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695966"
---
# <a name="repeatc-operation"></a><span data-ttu-id="4d1bf-102">RepeatC 操作</span><span class="sxs-lookup"><span data-stu-id="4d1bf-102">RepeatC operation</span></span>

<span data-ttu-id="4d1bf-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4d1bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4d1bf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d1bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d1bf-105">在给定的次数后重复操作。</span><span class="sxs-lookup"><span data-stu-id="4d1bf-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="4d1bf-106">输入</span><span class="sxs-lookup"><span data-stu-id="4d1bf-106">Input</span></span>

### <a name="op--tinput--unit-ctl"></a><span data-ttu-id="4d1bf-107">op： ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="4d1bf-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4d1bf-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="4d1bf-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="4d1bf-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d1bf-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d1bf-110">要调用的次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4d1bf-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="4d1bf-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="4d1bf-111">input : 'TInput</span></span>

<span data-ttu-id="4d1bf-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4d1bf-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d1bf-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d1bf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4d1bf-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="4d1bf-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="4d1bf-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="4d1bf-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="4d1bf-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d1bf-116">See Also</span></span>

- [<span data-ttu-id="4d1bf-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="4d1bf-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="4d1bf-118">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="4d1bf-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="4d1bf-119">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="4d1bf-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="4d1bf-120">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="4d1bf-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)