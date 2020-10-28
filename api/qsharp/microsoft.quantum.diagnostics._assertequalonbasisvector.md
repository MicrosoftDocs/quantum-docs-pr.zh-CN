---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695623"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


检查应用两个操作的结果 `givenU` 和 `expectedU` 基础状态是否相同。 基础状态由 `basis` 参数描述。
<xref:microsoft.quantum.extensions.fliptobasis>有关此说明的详细信息，请参阅函数。

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>输入

### <a name="basis--int"></a>basis： [Int](xref:microsoft.quantum.lang-ref.int)[]

Qubit 基础状态 ID 指定的基础状态 (0 <= id <= 3) 对于 $n $ qubits 中的每个。


### <a name="givenu--qubit--unit"></a>givenU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

要检查 $n $ qubits 上的操作。


### <a name="expectedu--qubit--unit-adj"></a>expectedU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

对 givenU 进行比较 $n $ qubits 上的引用操作。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

