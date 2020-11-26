---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b27759caba3c5dd363dbdf24d6e5de76870173cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200945"
---
# <a name="encodeintobitflipcode-operation"></a>EncodeIntoBitFlipCode 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


编码为 [3，1，3]/⟦3，1，1⟧位翻转代码。

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>输入

### <a name="physregister--qubit"></a>physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

物理 qubits 的寄存器，表示要保护的数据。


### <a name="auxqubits--qubit"></a>auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

最初在 $ \ket $ 状态中注册辅助 qubits，用于对 {00} 要保护的数据进行编码。



## <a name="output--logicalregister"></a>输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

编码中使用的物理和辅助 qubits，用逻辑寄存器表示。

## <a name="see-also"></a>另请参阅

- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)