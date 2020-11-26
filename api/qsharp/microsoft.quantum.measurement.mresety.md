---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227023"
---
# <a name="mresety-operation"></a>MResetY 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


按 Y 度量单个 qubit，并将其重置为测量后的固定初始状态。

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>描述

以 $Y $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。

## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要测量的单个 qubit。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__

Pauli 中测量的结果 `target` $Y $ basis。