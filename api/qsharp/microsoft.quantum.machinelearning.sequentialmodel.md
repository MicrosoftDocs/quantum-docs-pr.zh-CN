---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854896"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


描述一种量程分类器模型，该模型由一系列参数化和控制旋转、旋转角度的赋值和模型所识别的两个类之间的偏差构成。

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>命名项

### <a name="structure--controlledrotation"></a>结构： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

用于对输入进行分类的受控旋转序列。
### <a name="parameters--double"></a>参数： [Double](xref:microsoft.quantum.lang-ref.double)[]

向给定分类结构分配旋转角度。
### <a name="bias--double"></a>偏置： [Double](xref:microsoft.quantum.lang-ref.double)

此分类器识别的两个类之间的偏差。

## <a name="references"></a>参考

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)