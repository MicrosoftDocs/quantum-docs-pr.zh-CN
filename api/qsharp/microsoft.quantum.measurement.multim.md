---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695321"
---
# <a name="multim-operation"></a>MultiM 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

软件包 [](https://nuget.org/packages/)


按标准度量给定数组中的每个 qubit。

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>输入

### <a name="targets--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要测量的 qubits 数组。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__ []

度量结果的数组。