---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850624"
---
# <a name="applytoheadc-operation"></a>ApplyToHeadC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将操作应用到数组的第一个元素。

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>说明

给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Head(targets))` 。

## <a name="input"></a>输入

### <a name="op--t--unit--is-ctl"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl

要应用的操作。


### <a name="targets--t"></a>目标： t []

要应用第一个目标的目标数组 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)