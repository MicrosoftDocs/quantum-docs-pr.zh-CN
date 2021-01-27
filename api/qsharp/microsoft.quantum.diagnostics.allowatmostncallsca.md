---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853542"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="2dbc1-102">AllowAtMostNCallsCA 操作</span><span class="sxs-lookup"><span data-stu-id="2dbc1-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="2dbc1-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2dbc1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2dbc1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2dbc1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2dbc1-105">在对此操作及其 adjoint 的调用之间，断言给定的操作最多可调用特定次数。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="2dbc1-106">输入</span><span class="sxs-lookup"><span data-stu-id="2dbc1-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="2dbc1-107">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2dbc1-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2dbc1-108">可调用的最大次数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="2dbc1-109">op： ' TInput => ' TOutput 是形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2dbc1-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="2dbc1-110">要限制其调用的操作。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="2dbc1-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2dbc1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2dbc1-112">失败时要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2dbc1-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2dbc1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2dbc1-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="2dbc1-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="2dbc1-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="2dbc1-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="2dbc1-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="2dbc1-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="2dbc1-117">示例</span><span class="sxs-lookup"><span data-stu-id="2dbc1-117">Example</span></span>

<span data-ttu-id="2dbc1-118">以下代码片段在支持此诊断的计算机上执行时将失败：</span><span class="sxs-lookup"><span data-stu-id="2dbc1-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="2dbc1-119">备注</span><span class="sxs-lookup"><span data-stu-id="2dbc1-119">Remarks</span></span>

<span data-ttu-id="2dbc1-120">对于不支持此操作的目标，此操作可能会替换为不支持操作。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>