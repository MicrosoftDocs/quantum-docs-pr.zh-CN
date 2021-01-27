---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852227"
---
# <a name="repeata-operation"></a><span data-ttu-id="4adeb-102">RepeatA 操作</span><span class="sxs-lookup"><span data-stu-id="4adeb-102">RepeatA operation</span></span>

<span data-ttu-id="4adeb-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4adeb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4adeb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4adeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4adeb-105">在给定的次数后重复操作。</span><span class="sxs-lookup"><span data-stu-id="4adeb-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="4adeb-106">输入</span><span class="sxs-lookup"><span data-stu-id="4adeb-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="4adeb-107">op： ' TInput => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="4adeb-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4adeb-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="4adeb-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="4adeb-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4adeb-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4adeb-110">要调用的次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4adeb-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="4adeb-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="4adeb-111">input : 'TInput</span></span>

<span data-ttu-id="4adeb-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4adeb-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4adeb-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4adeb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4adeb-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="4adeb-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="4adeb-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="4adeb-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="4adeb-116">示例</span><span class="sxs-lookup"><span data-stu-id="4adeb-116">Example</span></span>

<span data-ttu-id="4adeb-117">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="4adeb-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="4adeb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4adeb-118">See Also</span></span>

- [<span data-ttu-id="4adeb-119">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="4adeb-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="4adeb-120">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="4adeb-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="4adeb-121">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="4adeb-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="4adeb-122">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="4adeb-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)