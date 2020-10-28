---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701069"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>ApplyXControlledOnTruthTableWithCleanTarget 操作

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


@"microsoft.quantum.intrinsic.x" `target` 如果布尔函数的 `func` 计算结果为 true （对于中的传统分配），则应用操作 `controlRegister` 。

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>说明

此操作实现了一种特殊情况 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ，在这种情况下，已知目标 qubit 为 $ \ket {0} $ 状态。

实现利用 @"microsoft.quantum.intrinsic.cnot" 和 @"microsoft.quantum.intrinsic.r1" 入口。  Adjoint 操作的实现经过了优化，并使用了基于度量值的 uncomputation。

## <a name="input"></a>输入

### <a name="func--bigint"></a>func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

表示为大整数的布尔事实数据表


### <a name="controlregister--qubit"></a>controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册控制 qubits


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

目标 qubit (必须处于 $ \ket {0} $ 状态) 



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [ApplyXControlledOnTruthTable。](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)