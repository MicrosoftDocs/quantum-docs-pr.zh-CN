---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700905"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


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

## <a name="remarks"></a>注解

如果为 `max <= min` ，则失败。

## <a name="see-also"></a>另请参阅

- [DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)