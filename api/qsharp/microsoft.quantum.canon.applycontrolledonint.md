---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845098"
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