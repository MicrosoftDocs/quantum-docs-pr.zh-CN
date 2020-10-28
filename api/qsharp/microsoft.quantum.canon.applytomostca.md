---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696196"
---
# <a name="applytomostca-operation"></a>ApplyToMostCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用到数组中除最后一个元素之外的所有元素。

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>说明

给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。

## <a name="input"></a>输入

### <a name="op--t--unit-adj--ctl"></a>op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要应用的操作。


### <a name="targets--t"></a>目标： t []

目标的数组，其中除最后一个外的所有将应用于 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToMost](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)