---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696691"
---
# <a name="drawcategorical-operation"></a>DrawCategorical 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


使用 probablities 列表指定的分类分布绘制随机样本。

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>说明

选择特定索引的概率与该索引处数组元素的值成正比。
将忽略等于零的数组元素并从不返回它们的索引。 如果任何数组元素小于0，或者如果没有数组元素大于零，则操作将失败。

## <a name="input"></a>输入

### <a name="probs--double"></a>probs： [Double](xref:microsoft.quantum.lang-ref.double)[]

浮点数的数组，与选择每个索引的概率成正比。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

一个整数 $i $ with probability $ \Pr (i) = p_i/\ sum_i p_i $，其中 $p _i $ 是的 $i $ th 元素 `probs` 。

## <a name="see-also"></a>另请参阅

- [CategoricalDistribution。](xref:Microsoft.Quantum.Random.CategoricalDistribution)