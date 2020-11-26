---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192853"
---
# <a name="maybechooseelement-operation"></a>MaybeChooseElement 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


给定一个数据数组和一个针对其索引的分布，尝试随机选择一个元素。

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>输入

### <a name="data--t"></a>数据： t []

应从中选择元素的数组。


### <a name="indexdistribution--discretedistribution"></a>indexDistribution： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

索引的分布 `data` 。



## <a name="output--boolt"></a>Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) 



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

