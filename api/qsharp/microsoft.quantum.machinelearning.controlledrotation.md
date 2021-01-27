---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847396"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


描述在其目标和控件索引、旋转轴和模型参数向量的索引方面的受控旋转。

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>命名项

### <a name="targetindex--int"></a>TargetIndex： [Int](xref:microsoft.quantum.lang-ref.int)

此受控旋转的目标 qubit 的索引。
### <a name="controlindices--int"></a>ControlIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]

此旋转的控件 qubit 索引的数组。
### <a name="axis--pauli"></a>轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

此旋转的轴。
### <a name="parameterindex--int"></a>ParameterIndex： [Int](xref:microsoft.quantum.lang-ref.int)

用于描述此旋转角度的模型参数向量的索引。

## <a name="example"></a>示例

以下内容表示对寄存器中第一个 qubit 的 $X $ 轴的旋转，在第二个 qubit 上控制，以及在顺序模型中使用第四个参数提供的角度：

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>备注

通过将设置 `ControlIndices` 为空的索引数组，可以表示无法控制的旋转 `new Int[0]` 。