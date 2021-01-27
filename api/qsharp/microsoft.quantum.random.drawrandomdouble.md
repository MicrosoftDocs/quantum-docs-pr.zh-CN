---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847623"
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

## <a name="example"></a>示例

以下 Q # 代码段随机绘制 $0 $ 和 $2 \pi $ 之间的角度：

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>备注

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)