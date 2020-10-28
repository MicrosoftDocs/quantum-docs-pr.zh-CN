---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701004"
---
# <a name="mresetx-operation"></a>MResetX 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

软件包 [](https://nuget.org/packages/)


在 X 基础上测量单个 qubit，并将其重置为固定的初始状态。

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>说明

以 $X $ 基数执行单 qubit 度量，并确保 qubit 返回到 {0} 度量值后的 $ \ket $。

## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要测量的单个 qubit。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__

Pauli 中测量的结果 `target` $X $ basis。