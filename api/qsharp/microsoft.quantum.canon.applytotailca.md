---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207847"
---
# <a name="applytotailca-operation"></a>ApplyToTailCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将操作应用到数组的最后一个元素。

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Tail(targets))` 。

## <a name="input"></a>输入

### <a name="op--t--unit--is-adj--ctl"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

要应用的操作。


### <a name="targets--t"></a>目标： t []

要应用最后一个目标的数组 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Canon. ApplyToTailA](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Canon. ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)