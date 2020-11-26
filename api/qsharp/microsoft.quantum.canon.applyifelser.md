---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209530"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用两个操作之一，具体取决于传统结果的值。

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>描述

如果结果为 `result` ，则在等于时应用该操作， `zeroOp` `zeroInput` `result` `Zero` 并应用 `oneOp(oneInput)` `result == One` 该操作。

## <a name="input"></a>输入

### <a name="result--__invalidresult__"></a>结果：__无效 <Result>__

用于确定是否应用或的测量 `zeroOp` 结果 `oneOp` 。


### <a name="zeroop--t--unit"></a>zeroOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 

在时要应用的操作 `result == Zero` 。


### <a name="zeroinput--t"></a>zeroInput： t

要提供给的 `zeroOp` 时间 `result == Zero` 。


### <a name="oneop--u--unit"></a>oneOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit) 

在时要应用的操作 `result == One` 。


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