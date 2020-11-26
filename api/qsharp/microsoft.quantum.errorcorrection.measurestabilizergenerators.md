---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200622"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


度量稳定组的给定生成器集。

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>输入

### <a name="stabilizergroup--pauli"></a>stabilizerGroup： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Multiqubit Pauli 运算符的数组。
例如， `stabilizerGroup[0]` 是一个 Qubit Pauli 矩阵列表，其中的 tensor 产品是一个稳定的生成器。


### <a name="logicalregister--logicalregister"></a>logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

定义了稳定程序代码的 qubits 的数组。


### <a name="gadget--pauliqubit--__invalidresult__"></a>小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__无效 <Result>__ 

一个操作，指定如何度量 multiqubit Pauli 运算符。



## <a name="output--syndrome"></a>输出： [症状](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

度量值的结果。

## <a name="remarks"></a>备注

这不会检查给定的生成器集是否上下班途中。
如果没有上下班途中，则测量结果可能是任意的。