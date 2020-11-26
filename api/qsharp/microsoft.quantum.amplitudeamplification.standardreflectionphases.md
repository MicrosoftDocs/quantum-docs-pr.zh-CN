---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191119"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


计算标准振幅放大的部分反射阶段。

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>输入

### <a name="niterations--int"></a>nIterations： [Int](xref:microsoft.quantum.lang-ref.int)

要为其生成部分反射阶段的波幅放大迭代数。



## <a name="output--reflectionphases"></a>输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

用于实现指定为部分反射的阶段的操作

## <a name="remarks"></a>备注

所有阶段都是 $ \pi $，除了第一次反射（对于开始状态）和最后一次反射（为 $0 $）。