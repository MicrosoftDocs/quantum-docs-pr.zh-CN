---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700565"
---
# <a name="localrotationslayer-function"></a>LocalRotationsLayer 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


返回一组不受 (控制的 qubit) 沿给定轴旋转的数组，并在寄存器中的每个 qubit 之间进行一次旋转，由不同的模型参数参数化。

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>输入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

给定层处理的 qubits 的数目。


### <a name="axis--pauli"></a>轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

给定层中每次旋转的旋转轴。



## <a name="output--controlledrotation"></a>Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

有关给定轴的受控旋转数组，每个 qubits 上一个轴 `nQubits` 。