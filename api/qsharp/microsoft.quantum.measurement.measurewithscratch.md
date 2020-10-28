---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696698"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

软件包 [](https://nuget.org/packages/)


使用显式暂存 qubit 度量给定的 Pauli 运算符以执行测量。

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]

指定为单一 qubit Pauli 运算符数组的多 qubit Pauli 运算符。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要测量的 Qubit 寄存器。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__

在收银机上测量给定 Pauli 运算符的结果 `target` 。