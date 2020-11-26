---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202560"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="6e71b-102">AllowAtMostNCallsCA 操作</span><span class="sxs-lookup"><span data-stu-id="6e71b-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="6e71b-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6e71b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6e71b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e71b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e71b-105">在对此操作及其 adjoint 的调用之间，断言给定的操作最多可调用特定次数。</span><span class="sxs-lookup"><span data-stu-id="6e71b-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6e71b-106">输入</span><span class="sxs-lookup"><span data-stu-id="6e71b-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="6e71b-107">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e71b-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e71b-108">可调用的最大次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6e71b-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="6e71b-109">op： ' TInput => ' TOutput 是形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="6e71b-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="6e71b-110">要限制其调用的操作。</span><span class="sxs-lookup"><span data-stu-id="6e71b-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="6e71b-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6e71b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6e71b-112">失败时要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="6e71b-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e71b-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e71b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6e71b-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="6e71b-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="6e71b-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="6e71b-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="6e71b-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="6e71b-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="6e71b-117">备注</span><span class="sxs-lookup"><span data-stu-id="6e71b-117">Remarks</span></span>

<span data-ttu-id="6e71b-118">对于不支持此操作的目标，此操作可能会替换为不支持操作。</span><span class="sxs-lookup"><span data-stu-id="6e71b-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>