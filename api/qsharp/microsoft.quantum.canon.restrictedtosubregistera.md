---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: c260a0e422d7ffb8137f6ac41e1cb398b2f4a2a7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852197"
---
# <a name="restrictedtosubregistera-function"></a>RestrictedToSubregisterA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将操作限制为寄存器的索引数组，即，subregister。
修饰符 `A` 指示操作为 adjointable。

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a>输入

### <a name="op--qubit--unit--is-adj"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

要限制为 subregister 的操作。


### <a name="idxs--int"></a>idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引数组，指示将对操作限制的 qubits。



## <a name="output--qubit--unit--is-adj"></a>Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词



## <a name="see-also"></a>另请参阅

- [Canon. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)