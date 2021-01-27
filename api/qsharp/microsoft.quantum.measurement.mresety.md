---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854636"
---
# <a name="mresety-operation"></a>MResetY 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


按 Y 度量单个 qubit，并将其重置为测量后的固定初始状态。

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>说明

以 $Y $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。

## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要测量的单个 qubit。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__

Pauli 中测量的结果 `target` $Y $ basis。