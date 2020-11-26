---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193074"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回在给定的非独占时间间隔内的统一分布。

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>输入

### <a name="min--double"></a>min： [Double](xref:microsoft.quantum.lang-ref.double)

要绘制的最小实数。


### <a name="max--double"></a>max： [Double](xref:microsoft.quantum.lang-ref.double)

要绘制的最大实数。



## <a name="output--continuousdistribution"></a>输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

一个分布，其随机 variates 是从到的非独占时间间隔中的实数 `min` `max` 。

## <a name="remarks"></a>备注

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)