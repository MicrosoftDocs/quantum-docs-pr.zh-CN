---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202101"
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