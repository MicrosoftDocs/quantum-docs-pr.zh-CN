---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696263"
---
# <a name="applyseriesofopsca-operation"></a>ApplySeriesOfOpsCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


在数组上按顺序应用 ops 及其目标的列表。  (Adjoint + 受控) 

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="listofops--t--unit-adj--ctl"></a>listOfOps： t [] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl []

要应用的 ops 列表，每个操作都采用 "t" 数组。 它们按顺序应用，最小索引优先。
每个都必须同时具有 Adjoint 和受控函子。


### <a name="targets--int"></a>目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []

描述 op 目标的嵌套数组。 每个数组都应包含一个整数列表，其中包含描述要使用的索引的整数。


### <a name="register--t"></a>注册： t []

要对其进行操作的 Qubit 寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="see-also"></a>另请参阅

- [Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)