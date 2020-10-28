---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695307"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


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