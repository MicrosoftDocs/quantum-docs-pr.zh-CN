---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853759"
---
# <a name="mresetx-operation"></a>MResetX 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


在 X 基础上测量单个 qubit，并将其重置为固定的初始状态。

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>说明

以 $X $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。

## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要测量的单个 qubit。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__

Pauli 中测量的结果 `target` $X $ basis。