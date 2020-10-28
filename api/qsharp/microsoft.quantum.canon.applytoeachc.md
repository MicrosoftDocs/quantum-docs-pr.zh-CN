---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696253"
---
# <a name="applytoeachc-operation"></a>ApplyToEachC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


对寄存器中的每个元素应用 qubit 操作。
修饰符 `C` 指示 qubit 操作可控制。

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="singleelementoperation--t--unit-ctl"></a>singleElementOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

操作的目标。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)