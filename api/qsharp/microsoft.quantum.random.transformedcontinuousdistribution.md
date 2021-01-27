---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857775"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


给定连续分布时，将返回一个新的分布，该分布通过给定函数转换原始。

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>输入

### <a name="transform--double---double"></a>转换： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)

将原始分布的 variates 转换为转换后的分布的函数。


### <a name="distribution--continuousdistribution"></a>分发： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

要转换的原始分布。



## <a name="output--continuousdistribution"></a>输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

由提供的转换与关联的新分布 `distribution` `transform` 。

## <a name="example"></a>示例

以下两个分布区完全相同：

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```