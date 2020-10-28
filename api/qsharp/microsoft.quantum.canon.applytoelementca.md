---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696236"
---
# <a name="applytoelementca-operation"></a>ApplyToElementCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用到数组的给定元素。

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>说明

给定一个操作 `op` 、一个索引 `index` 和一个目标数组 `targets` ，适用于 `op(targets[index])` 。

## <a name="input"></a>输入

### <a name="op--t--unit-adj--ctl"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要应用的操作。


### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)

目标数组中的索引。


### <a name="targets--t"></a>目标： t []

的可能目标的数组 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)