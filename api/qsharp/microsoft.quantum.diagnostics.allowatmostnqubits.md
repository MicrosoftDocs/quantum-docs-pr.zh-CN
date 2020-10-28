---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695609"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="b4fc7-102">AllowAtMostNQubits 操作</span><span class="sxs-lookup"><span data-stu-id="b4fc7-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="b4fc7-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b4fc7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b4fc7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4fc7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4fc7-105">在对此操作及其 adjoint 的调用之间，将使用语句最多地断言给定数量的附加 qubits。</span><span class="sxs-lookup"><span data-stu-id="b4fc7-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b4fc7-106">输入</span><span class="sxs-lookup"><span data-stu-id="b4fc7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b4fc7-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4fc7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4fc7-108">可分配的最大 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="b4fc7-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="b4fc7-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b4fc7-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b4fc7-110">失败时要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="b4fc7-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4fc7-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4fc7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b4fc7-112">注解</span><span class="sxs-lookup"><span data-stu-id="b4fc7-112">Remarks</span></span>

<span data-ttu-id="b4fc7-113">对于不支持此操作的目标，此操作可能会替换为不支持操作。</span><span class="sxs-lookup"><span data-stu-id="b4fc7-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>