---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192904"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


绘制给定范围内的随机整数。

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>输入

### <a name="min--int"></a>min： [Int](xref:microsoft.quantum.lang-ref.int)

要绘制的最小整数。


### <a name="max--int"></a>max： [Int](xref:microsoft.quantum.lang-ref.int)

要绘制的最大整数。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

中从到的一个整数，其值 `min` 为 `max` 统一的概率。

## <a name="remarks"></a>备注

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)