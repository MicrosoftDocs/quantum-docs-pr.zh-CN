---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696251"
---
# <a name="applytoeachca-operation"></a>ApplyToEachCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


对寄存器中的每个元素应用 qubit 操作。
修饰符 `CA` 指示 qubit 操作可控制和 adjointable。

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="singleelementoperation--t--unit-adj--ctl"></a>singleElementOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

操作的目标。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)