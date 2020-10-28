---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696308"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>ApplyMultiplyControlledLowDepthAnd 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


实现多控制的 Toffoli 入口，假定目标 qubit 初始化为0。  Adjoint 操作假定目标 qubit 将重置为0。  要求 Vny-rz-j42 深度为1，而 helper qubits 的数目在 qubits 数量上为指数。

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="controls--qubit"></a>控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

控件 qubits


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

目标 qubit



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

