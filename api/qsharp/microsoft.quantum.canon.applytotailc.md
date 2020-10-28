---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696168"
---
# <a name="applytotailc-operation"></a>ApplyToTailC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用到数组的最后一个元素。

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>说明

给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Tail(targets))` 。

## <a name="input"></a>输入

### <a name="op--t--unit-ctl"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

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
- [Canon. ApplyToTailCA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)