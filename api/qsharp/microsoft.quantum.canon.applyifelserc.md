---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696332"
---
# <a name="applyifelserc-operation"></a>ApplyIfElseRC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


应用两个可控操作之一，具体取决于古典结果的值。

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a>说明

如果结果为 `result` ，则在等于时应用该操作， `zeroOp` `zeroInput` `result` `Zero` 并应用 `oneOp(oneInput)` `result == One` 该操作。

## <a name="input"></a>输入

### <a name="result--__invalidresult__"></a>结果： __无效 <Result>__

用于确定是否应用或的测量 `zeroOp` 结果 `oneOp` 。


### <a name="zeroop--t--unit-ctl"></a>zeroOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

在时要应用的可控操作 `result == Zero` 。


### <a name="zeroinput--t"></a>zeroInput： t

要提供给的 `zeroOp` 时间 `result == Zero` 。


### <a name="oneop--u--unit-ctl"></a>oneOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

在时要应用的可控操作 `result == One` 。


### <a name="oneinput--u"></a>oneInput： ' U

要提供给的 `oneOp` 时间 `result == One` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

`zeroOp`要有条件地应用的操作的输入类型。
### <a name="u"></a>' U

`oneOp`要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)