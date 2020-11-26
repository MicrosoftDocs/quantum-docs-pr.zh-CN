---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201455"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow 操作

命名空间 [：](xref:Microsoft.Quantum.Environment)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回当前可用于借用的 qubits 的数目。

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

可以借用并且不会作为语句的一部分进行分配的 qubits 的数目 `borrowing` 。
如果正在使用的目标计算机未提供此信息，则 `-1` 返回。

## <a name="see-also"></a>另请参阅

- [GetQubitsAvailableToUse。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)