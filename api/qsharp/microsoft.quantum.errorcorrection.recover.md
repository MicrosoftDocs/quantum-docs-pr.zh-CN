---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 恢复操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: 3e2ce404ae3a6b4097897b859388fea3f915232c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825521"
---
# <a name="recover-operation"></a>恢复操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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