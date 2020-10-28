---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696370"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="6f0f1-102">ApplyControlledOnBitString 操作</span><span class="sxs-lookup"><span data-stu-id="6f0f1-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="6f0f1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6f0f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6f0f1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f0f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f0f1-105">对目标寄存器应用单一操作，该操作由给定位掩码指定的状态控制。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="6f0f1-106">输入</span><span class="sxs-lookup"><span data-stu-id="6f0f1-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="6f0f1-107">bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6f0f1-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6f0f1-108">用于控制给定单一操作的位字符串。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="6f0f1-109">oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="6f0f1-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6f0f1-110">要应用于目标寄存器的单一操作。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="6f0f1-111">controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6f0f1-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6f0f1-112">控制应用程序的量程寄存器 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="6f0f1-113">targetRegister： t</span><span class="sxs-lookup"><span data-stu-id="6f0f1-113">targetRegister : 'T</span></span>

<span data-ttu-id="6f0f1-114">要作为输入传递到的目标寄存器 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f0f1-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f0f1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6f0f1-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="6f0f1-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f0f1-117">找</span><span class="sxs-lookup"><span data-stu-id="6f0f1-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6f0f1-118">注解</span><span class="sxs-lookup"><span data-stu-id="6f0f1-118">Remarks</span></span>

<span data-ttu-id="6f0f1-119">给定的模式 `bits` 可能比更短 `controlRegister` ，在这种情况下，将 (忽略附加的 qubits，而不会在 $ \ket {0} $ 和 $ \ket $) 上进行控制 {1} 。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="6f0f1-120">如果 `bits` 的长度超过 `controlRegister` ，则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="6f0f1-121">例如， `bits = [0,1,0,0,1]` 表示 `oracle` 当且仅当 `controlRegister` 处于状态 $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $ 时应用。</span><span class="sxs-lookup"><span data-stu-id="6f0f1-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>