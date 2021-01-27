---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826324"
---
# <a name="encodeintofivequbitcode-operation"></a>EncodeIntoFiveQubitCode 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


编码为⟦5，1，3⟧量程代码。

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>输入

### <a name="physregister--qubit"></a>physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

表示未编码状态的 qubit。 此数组 `Qubit[]` 的长度为1。


### <a name="auxqubits--qubit"></a>auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

将用于表示编码状态的辅助 qubits 的注册。



## <a name="output--logicalregister"></a>输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

存储编码状态的类型的物理 qubits 数组 `LogicalRegister` 。

## <a name="see-also"></a>另请参阅

- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)