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
# <a name="applycontrolledonbitstring-operation"></a>ApplyControlledOnBitString 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


对目标寄存器应用单一操作，该操作由给定位掩码指定的状态控制。

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>输入

### <a name="bits--bool"></a>bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

用于控制给定单一操作的位字符串。


### <a name="oracle--t--unit-adj--ctl"></a>oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要应用于目标寄存器的单一操作。


### <a name="controlregister--qubit"></a>controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

控制应用程序的量程寄存器 `oracle` 。


### <a name="targetregister--t"></a>targetRegister： t

要作为输入传递到的目标寄存器 `oracle` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>注解

给定的模式 `bits` 可能比更短 `controlRegister` ，在这种情况下，将 (忽略附加的 qubits，而不会在 $ \ket {0} $ 和 $ \ket $) 上进行控制 {1} 。
如果 `bits` 的长度超过 `controlRegister` ，则会引发错误。

例如， `bits = [0,1,0,0,1]` 表示 `oracle` 当且仅当 `controlRegister` 处于状态 $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $ 时应用。