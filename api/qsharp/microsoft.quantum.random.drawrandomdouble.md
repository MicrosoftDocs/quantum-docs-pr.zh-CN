---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192938"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


以给定的非独占间隔绘制随机实数。

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>输入

### <a name="min--double"></a>min： [Double](xref:microsoft.quantum.lang-ref.double)

要绘制的最小实数。


### <a name="max--double"></a>max： [Double](xref:microsoft.quantum.lang-ref.double)

要绘制的最大实数。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

从到的非独占时间间隔内的随机实数 `min` `max` ，采用统一的概率。

## <a name="remarks"></a>备注

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)