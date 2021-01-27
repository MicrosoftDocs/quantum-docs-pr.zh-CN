---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852212"
---
# <a name="repeatca-operation"></a><span data-ttu-id="c449b-102">RepeatCA 操作</span><span class="sxs-lookup"><span data-stu-id="c449b-102">RepeatCA operation</span></span>

<span data-ttu-id="c449b-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c449b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c449b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c449b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c449b-105">在给定的次数后重复操作。</span><span class="sxs-lookup"><span data-stu-id="c449b-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c449b-106">输入</span><span class="sxs-lookup"><span data-stu-id="c449b-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="c449b-107">op： ' TInput => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c449b-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c449b-108">要重复调用的操作。</span><span class="sxs-lookup"><span data-stu-id="c449b-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="c449b-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c449b-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c449b-110">要调用的次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c449b-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="c449b-111">输入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="c449b-111">input : 'TInput</span></span>

<span data-ttu-id="c449b-112">要传递到的输入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c449b-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c449b-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c449b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c449b-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="c449b-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="c449b-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="c449b-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="c449b-116">示例</span><span class="sxs-lookup"><span data-stu-id="c449b-116">Example</span></span>

<span data-ttu-id="c449b-117">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="c449b-117">The following are equivalent:</span></span>

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="c449b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c449b-118">See Also</span></span>

- [<span data-ttu-id="c449b-119">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="c449b-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="c449b-120">Canon。重复</span><span class="sxs-lookup"><span data-stu-id="c449b-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="c449b-121">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="c449b-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="c449b-122">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="c449b-122">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)