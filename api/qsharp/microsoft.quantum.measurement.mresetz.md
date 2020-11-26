---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194128"
---
# <a name="mresetz-operation"></a>MResetZ 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


度量 Z 基准中的单个 qubit，并将其重置为固定的初始状态。

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>描述

以 $Z $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。

## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要测量的单个 qubit。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__

Pauli 中测量的结果 `target` $Z $ basis。