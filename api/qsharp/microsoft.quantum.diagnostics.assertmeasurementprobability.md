---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695598"
---
# <a name="assertmeasurementprobability-operation"></a>AssertMeasurementProbability 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


在给定 Pauli 基础上测量给定 qubits 的断言在某种程度上具有给定概率的给定结果。

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a>输入

### <a name="bases--pauli"></a>基： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

用于断言概率的度量效果，表示为多 qubit Pauli 运算符。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要对其进行断言的寄存器。


### <a name="result--__invalidresult__"></a>结果： __无效 <Result>__

的预期结果 `Measure(bases, qubits)` 。


### <a name="prob--double"></a>prob： [Double](xref:microsoft.quantum.lang-ref.double)

给定结果预计的概率。


### <a name="msg--string"></a>msg： [String](xref:microsoft.quantum.lang-ref.string)

断言失败时要报告的消息。


### <a name="tol--double"></a>tol： [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

请注意，此操作的 Adjoint 和受控版本将不检查该条件。

## <a name="see-also"></a>另请参阅

- [AssertMeasurement。](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)