---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226989"
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