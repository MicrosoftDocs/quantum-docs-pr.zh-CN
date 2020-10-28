---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695606"
---
# <a name="assertmeasurement-operation"></a>AssertMeasurement 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


度量给定 Pauli 基础中给定 qubits 的断言将始终具有给定的结果。

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a>输入

### <a name="bases--pauli"></a>基： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

用于断言概率的度量效果，表示为多 qubit Pauli 运算符。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要对其进行断言的寄存器。


### <a name="result--__invalidresult__"></a>结果： __无效 <Result>__

的预期结果 `Measure(bases, qubits)` 。


### <a name="msg--string"></a>msg： [String](xref:microsoft.quantum.lang-ref.string)

断言失败时要报告的消息。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

请注意，此操作的 Adjoint 和受控版本将不检查该条件。

## <a name="see-also"></a>另请参阅

- [AssertMeasurementProbability。](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)