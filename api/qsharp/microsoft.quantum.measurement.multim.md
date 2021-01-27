---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856996"
---
# <a name="multim-operation"></a>MultiM 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


按标准度量给定数组中的每个 qubit。

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>输入

### <a name="targets--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要测量的 qubits 数组。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__[]

度量结果的数组。