---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201404"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse 操作

命名空间 [：](xref:Microsoft.Quantum.Environment)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回当前可供使用的 qubits 的数目。

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

可在语句中分配的 qubits 的数目 `using` 。
如果正在使用的目标计算机未提供此信息，则 `-1` 返回。

## <a name="see-also"></a>另请参阅

- [GetQubitsAvailableToBorrow。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)