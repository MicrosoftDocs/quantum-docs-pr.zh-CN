---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695326"
---
# <a name="measureallz-operation"></a>MeasureAllZ 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

软件包 [](https://nuget.org/packages/)


共同度量 Pauli Z 基础的 qubits 寄存器。

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>说明

度量 $Z \otimes Z \otimes \cdots \otimes Z $ 基础中的 qubits 的寄存器，表示整个寄存器的奇偶校验。

## <a name="input"></a>输入

### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要测量的寄存器。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__

度量 $Z \otimes Z \otimes \cdots \otimes Z $ 的结果。