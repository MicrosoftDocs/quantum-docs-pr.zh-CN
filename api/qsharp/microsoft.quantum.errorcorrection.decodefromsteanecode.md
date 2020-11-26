---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 50fc6fb22e8b65ce10aba41e18362ad96236a907
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201132"
---
# <a name="decodefromsteanecode-operation"></a>DecodeFromSteaneCode 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


一种反向编码操作，它将未编码的量程寄存器映射到⟦7，1，3⟧ Steane 量程代码下的编码的量程寄存器。

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>输入

### <a name="logicalregister--logicalregister"></a>logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

表示已编码的 qubit 代码逻辑状态的 qubits 的数组。



## <a name="output--qubitqubit"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) 

长度为1的 qubit 数组，它表示第一个参数中未编码的状态，以及第二个参数中的辅助 qubits。

## <a name="remarks"></a>备注

所选的解码器使用⟦7，1，3⟧ Steane 代码的 CSS 代码属性，即，它会单独更正 X 错误和 Z 错误。 此代码的一个属性是，X 的位置分别是 x 的分别是 X 的3位编码，这是 X 的3位编码，被视为整数。

## <a name="references"></a>参考

- D. Gottesman、"稳定代码和量程错误纠正" 博士学位 Thesis，Caltech，1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>另请参阅

- [ErrorCorrection. SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)