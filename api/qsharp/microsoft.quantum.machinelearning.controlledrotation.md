---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196559"
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

## <a name="remarks"></a>备注

通过将设置 `ControlIndices` 为空的索引数组，可以表示无法控制的旋转 `new Int[0]` 。