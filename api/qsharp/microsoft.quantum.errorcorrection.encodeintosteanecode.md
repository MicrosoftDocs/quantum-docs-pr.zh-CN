---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826204"
---
# <a name="encodeintosteanecode-operation"></a>EncodeIntoSteaneCode 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


一种编码操作，用于将未编码的量程寄存器映射到⟦7，1，3⟧ Steane 量程代码下的编码的量程寄存器。

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>输入

### <a name="physregister--qubit"></a>physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

保留未编码的量程状态的 qubit 寄存器


### <a name="auxqubits--qubit"></a>auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 寄存器，它最初为零，并添加到量程系统以便可以执行编码操作



## <a name="output--logicalregister"></a>输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

应用 Steane 编码器后保持状态的量程寄存器

## <a name="see-also"></a>另请参阅

- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)