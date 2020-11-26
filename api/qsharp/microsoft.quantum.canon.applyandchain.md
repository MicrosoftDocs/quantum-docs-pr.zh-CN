---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219356"
---
# <a name="applyandchain-operation"></a>ApplyAndChain 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


计算和入口链

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a>描述

必须显式指定用于计算临时结果的辅助 qubits。
如果至少有两个控件，则该寄存器的长度为 `Length(ctrlRegister) - 2` ，否则长度为0。

## <a name="input"></a>输入

### <a name="auxregister--qubit"></a>auxRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="ctrlregister--qubit"></a>ctrlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

