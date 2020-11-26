---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193006"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="remarks"></a>备注

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)