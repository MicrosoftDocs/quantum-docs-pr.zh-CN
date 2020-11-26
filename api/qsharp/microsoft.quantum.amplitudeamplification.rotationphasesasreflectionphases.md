---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191187"
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