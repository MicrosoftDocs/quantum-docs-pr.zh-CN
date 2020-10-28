---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重置操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699784"
---
# <a name="reset-operation"></a>重置操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


给定单个 qubit，对其进行度量，并确保其处于 | 0 ⟩状态，以便可以安全地释放它。

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

其状态将重置为 $ \ket $ 的 qubit {0} 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

