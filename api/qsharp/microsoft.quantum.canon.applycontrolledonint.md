---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3dd17e6bc913e84941a6b81f134e60536a4c4122
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218999"
---
# <a name="applycontrolledonint-operation"></a>ApplyControlledOnInt 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果控件寄存器状态对应于指定的正整数，则对目标寄存器应用单一操作。

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="numberstate--int"></a>numberState： [Int](xref:microsoft.quantum.lang-ref.int)

应在其上控制操作的非负整数 `oracle` 。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

要控制的单一操作。


### <a name="controlregister--qubit"></a>controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

控制应用程序的量程寄存器 `oracle` 。


### <a name="targetregister--t"></a>targetRegister： t

要对其应用的寄存器 `oracle` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

的值 `numberState` 是使用小字节序编码来解释的。

`numberState` 最大必须为 $ 2 ^ \texttt{Length (controlRegister) }-$1。
例如， `numberState = 537` 表示 `oracle` 当且仅当 `controlRegister` 处于状态 $ \ket $ 时应用 {537} 。