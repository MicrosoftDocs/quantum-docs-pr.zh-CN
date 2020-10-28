---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695610"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="a04f5-102">AllowAtMostNCallsCA 操作</span><span class="sxs-lookup"><span data-stu-id="a04f5-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="a04f5-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a04f5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a04f5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a04f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a04f5-105">在对此操作及其 adjoint 的调用之间，断言给定的操作最多可调用特定次数。</span><span class="sxs-lookup"><span data-stu-id="a04f5-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a04f5-106">输入</span><span class="sxs-lookup"><span data-stu-id="a04f5-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="a04f5-107">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a04f5-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a04f5-108">可调用的最大次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="a04f5-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="a04f5-109">op： ' TInput => ' TOutput 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a04f5-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="a04f5-110">要限制其调用的操作。</span><span class="sxs-lookup"><span data-stu-id="a04f5-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="a04f5-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a04f5-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a04f5-112">失败时要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="a04f5-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a04f5-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a04f5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a04f5-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="a04f5-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="a04f5-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="a04f5-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="a04f5-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="a04f5-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="a04f5-117">注解</span><span class="sxs-lookup"><span data-stu-id="a04f5-117">Remarks</span></span>

<span data-ttu-id="a04f5-118">对于不支持此操作的目标，此操作可能会替换为不支持操作。</span><span class="sxs-lookup"><span data-stu-id="a04f5-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>