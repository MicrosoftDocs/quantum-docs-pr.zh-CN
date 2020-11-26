---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227074"
---
# <a name="measureallz-operation"></a>MeasureAllZ 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


共同度量 Pauli Z 基础的 qubits 寄存器。

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>描述

度量 $Z \otimes Z \otimes \cdots \otimes Z $ 基础中的 qubits 的寄存器，表示整个寄存器的奇偶校验。

## <a name="input"></a>输入

### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要测量的寄存器。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__

度量 $Z \otimes Z \otimes \cdots \otimes Z $ 的结果。