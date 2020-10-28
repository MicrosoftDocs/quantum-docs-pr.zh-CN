---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696343"
---
# <a name="applyifelsebca-operation"></a>ApplyIfElseBCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


应用两个单一操作之一，具体取决于传统位的值。

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a>说明

给定一个位，在为时 `bit` 应用该操作，并在为时应用该操作 `trueOp` `trueInput` `bit` `true` `falseOp(falseInput)` `bit` `false` 。

## <a name="input"></a>输入

### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

用于确定是否 `trueOp` 应用或的布尔值 `falseOp` 。


### <a name="trueop--t--unit-adj--ctl"></a>trueOp：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

在为时要应用的单一 `bit` 操作 `true` 。


### <a name="trueinput--t"></a>trueInput： t

当为时要向其提供的输入 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit-adj--ctl"></a>falseOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

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