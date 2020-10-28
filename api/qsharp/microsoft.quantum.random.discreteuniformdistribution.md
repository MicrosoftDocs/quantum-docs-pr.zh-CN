---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696693"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


返回在给定的非独占范围内的统一分布。

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>输入

### <a name="min--int"></a>min： [Int](xref:microsoft.quantum.lang-ref.int)

要绘制的最小整数。


### <a name="max--int"></a>max： [Int](xref:microsoft.quantum.lang-ref.int)

要绘制的最大整数。



## <a name="output--discretedistribution"></a>输出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

一种分布，其随机 variates 是从到的非独占概率中的整数 `min` `max` 。

## <a name="remarks"></a>注解

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)