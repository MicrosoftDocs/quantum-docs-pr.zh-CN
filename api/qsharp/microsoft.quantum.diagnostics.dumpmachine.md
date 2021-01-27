---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853421"
---
# <a name="dumpmachine-function"></a>DumpMachine 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


转储当前目标计算机的状态。

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>输入

### <a name="location--t"></a>位置：否

提供有关在何处生成计算机转储的信息。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

无。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

此方法允许您将有关目标计算机的当前状态的信息转储到文件或其他位置。
生成的实际信息和的语义 `location` 特定于每个目标计算机。 但是，提供空元组作为位置 (`()`) 或仅省略 `location` 参数通常意味着将输出生成到控制台。

对于作为量程开发工具包的一部分分发的本地完整状态模拟器，此方法需要一个带有文件路径的字符串，它将波形函数编写为一维复数数组，其中每个元素都表示测量相应状态的概率的 amplitudes。