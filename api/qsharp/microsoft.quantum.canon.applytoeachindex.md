---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844596"
---
# <a name="applytoeachindex-operation"></a>ApplyToEachIndex 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将单 qubit 操作应用于寄存器中的每个索引元素。

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="singleelementoperation--intt--unit"></a>singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个操作操作的目标。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [Canon. ApplyToEachIndexA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [Canon. ApplyToEachIndexC](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [Canon. ApplyToEachIndexCA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)