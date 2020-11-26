---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217860"
---
# <a name="applytoeach-operation"></a>ApplyToEach 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对寄存器中的每个元素应用 qubit 操作。

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>输入

### <a name="singleelementoperation--t--unit"></a>singleElementOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

操作的目标。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEachC](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Canon. ApplyToEachA](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Canon. ApplyToEachCA](xref:Microsoft.Quantum.Canon.ApplyToEachCA)