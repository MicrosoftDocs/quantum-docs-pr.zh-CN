---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695091"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


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

## <a name="remarks"></a>注解

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)