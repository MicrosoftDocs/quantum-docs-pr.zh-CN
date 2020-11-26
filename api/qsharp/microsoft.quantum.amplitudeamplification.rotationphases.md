---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191357"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases 用户定义的类型

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


振幅放大中 qubit 旋转序列的各个阶段。

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>备注

第一个参数是一个用于反射的阶段数组，表示为一个 qubit 旋转的积。
[ G.H. 低，I. L。 语， https://arxiv.org/abs/1707.05391 ]。