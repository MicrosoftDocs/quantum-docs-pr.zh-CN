---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: bac763168dbc7379691f850a79cbb6e61639ba89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841791"
---
# <a name="applyifelserc-operation"></a>ApplyIfElseRC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用两个可控操作之一，具体取决于古典结果的值。

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>说明

如果结果为 `result` ，则在等于时应用该操作， `zeroOp` `zeroInput` `result` `Zero` 并应用 `oneOp(oneInput)` `result == One` 该操作。

## <a name="input"></a>输入

### <a name="result--__invalidresult__"></a>结果：__无效 <Result>__

用于确定是否应用或的测量 `zeroOp` 结果 `oneOp` 。


### <a name="zeroop--t--unit--is-ctl"></a>zeroOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl

在时要应用的可控操作 `result == Zero` 。


### <a name="zeroinput--t"></a>zeroInput： t

要提供给的 `zeroOp` 时间 `result == Zero` 。


### <a name="oneop--u--unit--is-ctl"></a>oneOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl

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