---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696248"
---
# <a name="applytoeachindexc-operation"></a>ApplyToEachIndexC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将单 qubit 操作应用于寄存器中的每个索引元素。
修饰符 `C` 指示 qubit 操作可控制。

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="singleelementoperation--intt--unit-ctl"></a>singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，不) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个操作操作的目标。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)