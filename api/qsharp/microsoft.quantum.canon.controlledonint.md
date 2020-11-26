---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207252"
---
# <a name="controlledonint-function"></a>ControlledOnInt 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果控件注册状态对应于指定的正整数，则返回一个单一运算符，该运算符应用目标寄存器上的 oracle。

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="numberstate--int"></a>numberState： [Int](xref:microsoft.quantum.lang-ref.int)

正整数。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

单一运算符。



## <a name="output--qubitt--unit--is-adj--ctl"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，不) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

`oracle`当控件注册状态对应于数字状态时，应用于目标寄存器的单一运算符 `numberState` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

的值 `numberState` 是使用小字节序编码来解释的。