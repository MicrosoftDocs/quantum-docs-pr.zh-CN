---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: eb01b1b9fccc19f0e3f1fd5ee596b95d0d61563f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200537"
---
# <a name="recovercss-operation"></a>RecoverCSS 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


按类型描述的量程代码执行一轮错误更正 `CSS` 。

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>输入

### <a name="code--css"></a>代码： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

封装为类型的量程 CSS 错误更正代码 `CSS` 描述了量程数据的编码和解码，以及如何测量 syndromes 错误。


### <a name="fnx--recoveryfn"></a>fnX： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

一个 `RecoveryFn` ，它将每个 $X $ 错误症状映射到 `Pauli[]` 更正检测到的错误的操作。


### <a name="fnz--recoveryfn"></a>fnZ： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

一个 `RecoveryFn` ，它将每个 $Z $ 错误症状映射到 `Pauli[]` 更正检测到的错误的操作。


### <a name="logicalregister--logicalregister"></a>logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

定义了稳定程序代码的 qubits 的数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [ErrorCorrection。](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)