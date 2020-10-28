---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696019"
---
# <a name="logicalandmeasandfix-operation"></a>LogicalANDMeasAndFix 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


计算多个 qubits 的逻辑 AND。

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="ctrlregister--qubit"></a>ctrlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits 输入到多输入和入口。


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要将和写入到的 Qubit。 假设此项始终以 $ \ket {0} $ 状态启动。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

当 `ctrlRegister` 正好为 $2 $ qubits 时，此项等效于操作，阶段为： $ `CCNOT` \ket {001} $ 和 $ \ket $ 上的 $ $ 和 $-e ^ {i \ pi/2} $ 上的阶段 $e ^ {i \ pi/2} $ {101} {011} 。
Adjoint 也是度量和修复方法，它仅在特殊情况下才是原始操作的逆操作 (参阅引用) ，但使用的 T-sql 更少。

## <a name="references"></a>参考

- [*Craig Gidney* ，1709.06648](https://arxiv.org/abs/1709.06648)