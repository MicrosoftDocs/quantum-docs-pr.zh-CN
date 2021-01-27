---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829229"
---
# <a name="dumpregister-function"></a>DumpRegister 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


将当前目标计算机的状态转储为与给定的 qubits 相关联。

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="location--t"></a>位置：否

提供有关在何处生成状态转储的信息。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要报告的 qubits 的列表。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

无。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

此方法允许你将与给定 qubits 的状态关联的信息转储到一个文件或其他位置。
生成的实际信息和的语义 `location` 特定于每个目标计算机。 但是，将空元组作为位置 (提供 `()`) 通常表示生成到控制台的输出。

对于作为量程开发工具包的一部分分发的本地完整状态模拟器，此方法需要一个字符串路径与文件的路径，在该文件中，它将写入给定)  (qubits 的状态，其中，每个元素都表示测量相应状态的概率的 amplitudes，其中每个元素表示测量相应状态的概率的。
如果给定的 qubits 与一些其他 qubit 放大，且无法分离其状态，则只会报告 qubits 为放大。