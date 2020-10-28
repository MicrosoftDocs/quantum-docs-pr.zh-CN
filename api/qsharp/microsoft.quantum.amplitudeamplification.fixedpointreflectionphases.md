---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700105"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

软件包 [](https://nuget.org/packages/)


计算固定点幅度放大的部分反射阶段。

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>输入

### <a name="nqueries--int"></a>nQueries： [Int](xref:microsoft.quantum.lang-ref.int)

Oracle 状态准备的查询数。 必须是奇整数。


### <a name="successmin--double"></a>successMin： [Double](xref:microsoft.quantum.lang-ref.double)

最小成功概率。



## <a name="output--reflectionphases"></a>输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

可在定点波幅放大量程算法实现中使用的阶段数组。

## <a name="references"></a>参考

我们使用 "使用最佳查询数进行定点的固定点放大" 中的阶段

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 另请参阅 "复合量程入口方法"
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) 的 `RotationPhases` 格式为。