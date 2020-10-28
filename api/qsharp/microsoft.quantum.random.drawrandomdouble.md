---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700713"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


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

## <a name="remarks"></a>注解

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)