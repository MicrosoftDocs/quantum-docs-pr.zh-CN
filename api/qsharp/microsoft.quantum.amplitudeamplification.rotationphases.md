---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843965"
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