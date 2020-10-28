---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695541"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse 操作

命名空间 [：](xref:Microsoft.Quantum.Environment)

软件包 [](https://nuget.org/packages/)


返回当前可供使用的 qubits 的数目。

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

可在语句中分配的 qubits 的数目 `using` 。
如果正在使用的目标计算机未提供此信息，则 `-1` 返回。

## <a name="see-also"></a>另请参阅

- [GetQubitsAvailableToBorrow。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)