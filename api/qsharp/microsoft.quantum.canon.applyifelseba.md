---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: 74d43344481c5a808e84ce9c9e36fa3e83cd0d89
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218659"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用两个 adjointable 操作之一，具体取决于传统位的值。

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a>描述

给定一个位，在为时 `bit` 应用该操作，并在为时应用该操作 `trueOp` `trueInput` `bit` `true` `falseOp(falseInput)` `bit` `false` 。

## <a name="input"></a>输入

### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

用于确定是否 `trueOp` 应用或的布尔值 `falseOp` 。


### <a name="trueop--t--unit--is-adj"></a>trueOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

当为时要应用的 adjointable `bit` 操作 `true` 。


### <a name="trueinput--t"></a>trueInput： t

当为时要向其提供的输入 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit--is-adj"></a>falseOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

当为时要应用的 adjointable `bit` 操作 `false` 。


### <a name="falseinput--u"></a>falseInput： ' U

当为时要向其提供的输入 `falseOp` `bit` `false` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

`trueOp`要有条件地应用的操作的输入类型。
### <a name="u"></a>' U

`falseOp`要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)