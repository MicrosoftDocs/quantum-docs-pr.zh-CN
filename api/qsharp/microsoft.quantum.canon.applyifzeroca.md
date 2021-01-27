---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: ApplyIfZeroCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4ed0660e2fe3623d0a8e4e4f3bd0bddb536b7b5c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844883"
---
# <a name="applyifzeroca-operation"></a>ApplyIfZeroCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用在传统结果值为零的条件运算。

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `Zero` 。 如果 `One` 为，则不会发生任何事情 `target` 。
后缀 `CA` 指示要应用的操作是单一 (可控和 adjointable) 。

## <a name="input"></a>输入

### <a name="result--__invalidresult__"></a>结果：__无效 <Result>__

用于控制是否应用 op 的测量结果。


### <a name="op--t--unit--is-adj--ctl"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

要有条件地应用的操作。


### <a name="target--t"></a>目标： t

将操作应用到的输入。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Canon. ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)