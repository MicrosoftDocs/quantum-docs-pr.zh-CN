---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844605"
---
# <a name="applytoeacha-operation"></a>ApplyToEachA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对寄存器中的每个元素应用 qubit 操作。
修饰符 `A` 指示 qubit 操作是 adjointable。

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>输入

### <a name="singleelementoperation--t--unit--is-adj"></a>singleElementOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

要应用到每个 qubit 的操作。


### <a name="register--t"></a>注册： t []

要在其上应用给定操作的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

操作的目标。

## <a name="example"></a>示例

准备 qubit $ \ket{+} $ 状态：

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)