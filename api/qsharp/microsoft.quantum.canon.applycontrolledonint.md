---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696369"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="49d21-102">ApplyControlledOnInt 操作</span><span class="sxs-lookup"><span data-stu-id="49d21-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="49d21-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49d21-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49d21-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49d21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49d21-105">如果控件寄存器状态对应于指定的正整数，则对目标寄存器应用单一操作。</span><span class="sxs-lookup"><span data-stu-id="49d21-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="49d21-106">输入</span><span class="sxs-lookup"><span data-stu-id="49d21-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="49d21-107">numberState： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49d21-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49d21-108">应在其上控制操作的非负整数 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="49d21-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="49d21-109">oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="49d21-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="49d21-110">要控制的单一操作。</span><span class="sxs-lookup"><span data-stu-id="49d21-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="49d21-111">controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="49d21-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="49d21-112">控制应用程序的量程寄存器 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="49d21-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="49d21-113">targetRegister： t</span><span class="sxs-lookup"><span data-stu-id="49d21-113">targetRegister : 'T</span></span>

<span data-ttu-id="49d21-114">要对其应用的寄存器 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="49d21-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49d21-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49d21-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="49d21-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="49d21-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49d21-117">找</span><span class="sxs-lookup"><span data-stu-id="49d21-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="49d21-118">注解</span><span class="sxs-lookup"><span data-stu-id="49d21-118">Remarks</span></span>

<span data-ttu-id="49d21-119">的值 `numberState` 是使用小字节序编码来解释的。</span><span class="sxs-lookup"><span data-stu-id="49d21-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="49d21-120">`numberState` 最大必须为 $ 2 ^ \texttt{Length (controlRegister) }-$1。</span><span class="sxs-lookup"><span data-stu-id="49d21-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="49d21-121">例如， `numberState = 537` 表示 `oracle` 当且仅当 `controlRegister` 处于状态 $ \ket $ 时应用 {537} 。</span><span class="sxs-lookup"><span data-stu-id="49d21-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>