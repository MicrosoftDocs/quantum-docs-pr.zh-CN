---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843956"
---
# <a name="rotationphasesasreflectionphases-function"></a>RotationPhasesAsReflectionPhases 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将指定为单一 qubit 旋转的阶段转换为指定为部分反射的阶段。

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>输入

### <a name="rotphases--rotationphases"></a>rotPhases： [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

要转换为部分反射的 qubit 旋转的数组。



## <a name="output--reflectionphases"></a>输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

用于实现指定为部分反射的阶段的操作。

## <a name="references"></a>参考

我们使用中的约定

- [ *G.H. Low，语*](https://arxiv.org/abs/1707.05391)将 qubit 循环阶段与反射运算符阶段相关联。