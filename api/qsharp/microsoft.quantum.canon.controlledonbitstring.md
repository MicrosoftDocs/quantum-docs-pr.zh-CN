---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216653"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果控件注册状态对应于指定的位掩码，则返回在目标寄存器上应用 oracle 的单一操作。

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>描述

此函数的输出是一个可以由单一转换 $U $ 进行表示的操作，此操作可由 \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{cases} \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1} ) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{cases}，\end{align}，其中 $V $ 是表示操作操作的单一转换 `oracle` 。

## <a name="input"></a>输入

### <a name="bits--bool"></a>bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

用于控制给定单一操作的位字符串。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

要应用于目标寄存器的单一操作。



## <a name="output--qubitt--unit--is-adj--ctl"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，不) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

`oracle`当控件注册状态对应于位掩码时，适用于目标寄存器的单一操作 `bits` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

给定的模式 `bits` 可能比更短 `controlRegister` ，在这种情况下，将 (忽略附加的 qubits，而不会在 $ \ket {0} $ 和 $ \ket $) 上进行控制 {1} 。
如果 `bits` 的长度超过 `controlRegister` ，则会引发错误。

给定布尔数组 `bits` 和单一操作 `oracle` ，此函数的输出是执行以下步骤的操作：

* 将 `X` 操作应用到控制寄存器的每个 qubit，该控件寄存器对应于 `false` 的元素 `bits` ;
* 应用于 `Controlled oracle` 控件和目标寄存器;
* 将操作应用于 `X` 控件注册的每个 qubit，该控件注册再次对应于 `false` 的元素， `bits` 以将控制寄存器返回到原始状态。

函子的输出 `Controlled` 是的一种特殊情况， `ControlledOnBitString` 其中， `bits` 等于 `[true, ..., true]` 。