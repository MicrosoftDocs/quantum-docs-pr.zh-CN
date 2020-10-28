---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696249"
---
# <a name="applytoeachindexa-operation"></a>ApplyToEachIndexA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将单 qubit 操作应用于寄存器中的每个索引元素。
修饰符 `A` 指示 qubit 操作是 adjointable。

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="singleelementoperation--intt--unit-adj"></a>singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，不) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个操作操作的目标。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)