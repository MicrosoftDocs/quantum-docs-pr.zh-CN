---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 恢复操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695488"
---
# <a name="recover-operation"></a>恢复操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

软件包 [](https://nuget.org/packages/)


按类型描述的量程代码执行一轮错误更正 `QECC` 。

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>输入

### <a name="code--qecc"></a>代码： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

打包为类型的量程错误更正代码 `QECC` 描述了量程数据的编码和解码，以及如何测量 syndromes 错误。


### <a name="fn--recoveryfn"></a>fn： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

一个 `RecoveryFn` ，它将每个错误症状映射到 `Pauli[]` 更正检测到的错误的操作。


### <a name="logicalregister--logicalregister"></a>logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

定义了稳定程序代码的 qubits 的数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [ErrorCorrection. QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)