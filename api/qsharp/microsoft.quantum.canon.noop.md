---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205960"
---
# <a name="noop-operation"></a>NoOp 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


对参数执行 (no op) 的标识操作。

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

此操作采用任何类型的值，但不执行任何操作。
这在需要输入操作类型时非常有用，但不应采取任何措施。
例如，如果特定错误更正症状指示未发生错误， `NoOp<Qubit[]>` 则可能是正确的恢复过程。
同样，如果某个操作需要状态准备过程作为输入，则 `NoOp<Qubit[]>` 可使用来准备状态 $ \ket{0 \cdots 0} $。

## <a name="input"></a>输入

### <a name="input--t"></a>输入： t

要忽略的值。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

几乎在所有情况下，都 `NoOp` 需要显式指定的类型参数。 例如，与 `NoOp<Qubit>` 相同 <xref:microsoft.quantum.intrinsic.i> 。

## <a name="see-also"></a>另请参阅

- [。 I](xref:Microsoft.Quantum.Intrinsic.I)