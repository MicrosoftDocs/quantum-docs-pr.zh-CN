---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827801"
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