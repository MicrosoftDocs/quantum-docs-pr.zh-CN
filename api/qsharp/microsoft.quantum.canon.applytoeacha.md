---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696255"
---
# <a name="applytoeacha-operation"></a>ApplyToEachA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


对寄存器中的每个元素应用 qubit 操作。
修饰符 `A` 指示 qubit 操作是 adjointable。

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="singleelementoperation--t--unit-adj"></a>singleElementOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

操作的目标。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)