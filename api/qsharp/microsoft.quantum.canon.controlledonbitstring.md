---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840803"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="bd013-102">ControlledOnBitString 函数</span><span class="sxs-lookup"><span data-stu-id="bd013-102">ControlledOnBitString function</span></span>

<span data-ttu-id="bd013-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd013-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd013-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd013-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd013-105">如果控件注册状态对应于指定的位掩码，则返回在目标寄存器上应用 oracle 的单一操作。</span><span class="sxs-lookup"><span data-stu-id="bd013-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="bd013-106">说明</span><span class="sxs-lookup"><span data-stu-id="bd013-106">Description</span></span>

<span data-ttu-id="bd013-107">此函数的输出是一个可以由单一转换 $U $ 进行表示的操作，此操作可由 \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{cases} \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1} ) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{cases}，\end{align}，其中 $V $ 是表示操作操作的单一转换 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="bd013-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="bd013-108">输入</span><span class="sxs-lookup"><span data-stu-id="bd013-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="bd013-109">bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="bd013-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="bd013-110">用于控制给定单一操作的位字符串。</span><span class="sxs-lookup"><span data-stu-id="bd013-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="bd013-111">oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="bd013-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bd013-112">要应用于目标寄存器的单一操作。</span><span class="sxs-lookup"><span data-stu-id="bd013-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="bd013-113">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，不) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="bd013-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bd013-114">`oracle`当控件注册状态对应于位掩码时，适用于目标寄存器的单一操作 `bits` 。</span><span class="sxs-lookup"><span data-stu-id="bd013-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd013-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="bd013-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd013-116">找</span><span class="sxs-lookup"><span data-stu-id="bd013-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="bd013-117">示例</span><span class="sxs-lookup"><span data-stu-id="bd013-117">Example</span></span>

<span data-ttu-id="bd013-118">以下代码片段是等效的：</span><span class="sxs-lookup"><span data-stu-id="bd013-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="bd013-119">和</span><span class="sxs-lookup"><span data-stu-id="bd013-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="bd013-120">以下代码准备状态 $ \frac {1} {2} ( \ket {00} -\ket {01} + \ket {10} + \ket {11}) $：</span><span class="sxs-lookup"><span data-stu-id="bd013-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="bd013-121">备注</span><span class="sxs-lookup"><span data-stu-id="bd013-121">Remarks</span></span>

<span data-ttu-id="bd013-122">给定的模式 `bits` 可能比更短 `controlRegister` ，在这种情况下，将 (忽略附加的 qubits，而不会在 $ \ket {0} $ 和 $ \ket $) 上进行控制 {1} 。</span><span class="sxs-lookup"><span data-stu-id="bd013-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="bd013-123">如果 `bits` 的长度超过 `controlRegister` ，则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="bd013-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="bd013-124">给定布尔数组 `bits` 和单一操作 `oracle` ，此函数的输出是执行以下步骤的操作：</span><span class="sxs-lookup"><span data-stu-id="bd013-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="bd013-125">将 `X` 操作应用到控制寄存器的每个 qubit，该控件寄存器对应于 `false` 的元素 `bits` ;</span><span class="sxs-lookup"><span data-stu-id="bd013-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="bd013-126">应用于 `Controlled oracle` 控件和目标寄存器;</span><span class="sxs-lookup"><span data-stu-id="bd013-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="bd013-127">将操作应用于 `X` 控件注册的每个 qubit，该控件注册再次对应于 `false` 的元素， `bits` 以将控制寄存器返回到原始状态。</span><span class="sxs-lookup"><span data-stu-id="bd013-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="bd013-128">函子的输出 `Controlled` 是的一种特殊情况， `ControlledOnBitString` 其中， `bits` 等于 `[true, ..., true]` 。</span><span class="sxs-lookup"><span data-stu-id="bd013-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>