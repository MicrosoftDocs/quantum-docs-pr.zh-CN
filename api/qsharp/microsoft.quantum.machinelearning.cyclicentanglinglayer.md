---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847386"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


返回沿给定轴进行了单独控制的旋转的数组，将循环排列在 qubits 的寄存器中，并通过不同的模型参数进行参数化。

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>输入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

给定层处理的 qubits 的数目。


### <a name="axis--pauli"></a>轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

给定层中每次旋转的旋转轴。


### <a name="stride--int"></a>步幅： [Int](xref:microsoft.quantum.lang-ref.int)

每个旋转的目标索引和控件索引之间的分隔。



## <a name="output--controlledrotation"></a>Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

跨 qubits 寄存器布局循环的由两个 qubit 控制的循环组成的数组 `nQubits` 。

## <a name="example"></a>示例

以下项是等效的：

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```