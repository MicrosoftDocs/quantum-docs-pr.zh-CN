---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 3ed9d7cbf277f4c3acd0e6c3b5f920c3e140855d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844972"
---
# <a name="applyifelsebca-operation"></a>ApplyIfElseBCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用两个单一操作之一，具体取决于传统位的值。

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

给定一个位，在为时 `bit` 应用该操作，并在为时应用该操作 `trueOp` `trueInput` `bit` `true` `falseOp(falseInput)` `bit` `false` 。

## <a name="input"></a>输入

### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

用于确定是否 `trueOp` 应用或的布尔值 `falseOp` 。


### <a name="trueop--t--unit--is-adj--ctl"></a>trueOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

在为时要应用的单一 `bit` 操作 `true` 。


### <a name="trueinput--t"></a>trueInput： t

当为时要向其提供的输入 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit--is-adj--ctl"></a>falseOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

在为时要应用的单一 `bit` 操作 `false` 。


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