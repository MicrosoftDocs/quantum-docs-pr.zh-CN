---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856115"
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



## <a name="example"></a>示例

以下 Q # 代码段从数组中随机选择一个元素：

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```