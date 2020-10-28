---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696729"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


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