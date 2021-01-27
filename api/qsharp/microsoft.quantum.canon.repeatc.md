---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: efb820411be63352fc09ada2441a9140dd5575f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840241"
---
# <a name="repeatc-operation"></a><span data-ttu-id="0607f-102">RepeatC 操作</span><span class="sxs-lookup"><span data-stu-id="0607f-102">RepeatC operation</span></span>

<span data-ttu-id="0607f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0607f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0607f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0607f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0607f-105">在给定的次数后重复操作。</span><span class="sxs-lookup"><span data-stu-id="0607f-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="0607f-106">输入</span><span class="sxs-lookup"><span data-stu-id="0607f-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="0607f-107">op： ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="0607f-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0607f-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="0607f-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="0607f-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0607f-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0607f-110">要调用的次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="0607f-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="0607f-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="0607f-111">input : 'TInput</span></span>

<span data-ttu-id="0607f-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="0607f-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0607f-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0607f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0607f-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="0607f-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="0607f-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="0607f-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="0607f-116">示例</span><span class="sxs-lookup"><span data-stu-id="0607f-116">Example</span></span>

<span data-ttu-id="0607f-117">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="0607f-117">The following are equivalent:</span></span>

```qsharp
RepeatC(U, 17, target);
(BoundC(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="0607f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0607f-118">See Also</span></span>

- [<span data-ttu-id="0607f-119">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="0607f-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="0607f-120">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="0607f-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="0607f-121">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="0607f-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="0607f-122">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="0607f-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)