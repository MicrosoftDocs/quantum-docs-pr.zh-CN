---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695542"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow 操作

命名空间 [：](xref:Microsoft.Quantum.Environment)

软件包 [](https://nuget.org/packages/)


返回当前可用于借用的 qubits 的数目。
这包括未使用的 qubits;也就是说，这包括由返回的 qubits `GetQubitsAvailableToUse` 。

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

可在语句中分配的 qubits 的数目 `borrowing` 。
如果正在使用的目标计算机未提供此信息，则 `-1` 返回。

## <a name="see-also"></a>另请参阅

- [GetQubitsAvailableToUse。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)