---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: e16254154909eb844164538acb7b82fedc11f86a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696350"
---
# <a name="applyifc-operation"></a>ApplyIfC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


应用采用传统位的可控操作。

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>说明

给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。 如果 `false` 为，则不会发生任何事情 `target` 。
后缀 `C` 指示要应用的操作可控制。

## <a name="input"></a>输入

### <a name="op--t--unit-ctl"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

要有条件地应用的操作。


### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

用于控制是否应用 op 的布尔值。


### <a name="target--t"></a>目标： t

将操作应用到的输入。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)