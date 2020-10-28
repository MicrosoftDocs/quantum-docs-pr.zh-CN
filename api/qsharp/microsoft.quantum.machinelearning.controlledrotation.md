---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695367"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


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

## <a name="remarks"></a>注解

通过将设置 `ControlIndices` 为空的索引数组，可以表示无法控制的旋转 `new Int[0]` 。