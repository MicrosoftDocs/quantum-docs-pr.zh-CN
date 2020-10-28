---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700080"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases 用户定义的类型

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

软件包 [](https://nuget.org/packages/)


振幅放大中 qubit 旋转序列的各个阶段。

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>注解

第一个参数是一个用于反射的阶段数组，表示为一个 qubit 旋转的积。
[ G.H. 低，I. L。 语， https://arxiv.org/abs/1707.05391 ]。