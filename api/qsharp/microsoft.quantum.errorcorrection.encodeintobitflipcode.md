---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 44034a864c946a7d3dbb21bad5ee500660709f1a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826682"
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