---
uid: Microsoft.Quantum.Random.ContinuousDistribution
title: ContinuousDistribution 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousDistribution
qsharp.summary: Represents a univariate probability distribution over real numbers.
ms.openlocfilehash: fa2c13f8b5205011476ab1ab3cf2440ca163bc27
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210227"
---
# <a name="continuousdistribution-user-defined-type"></a>ContinuousDistribution 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


表示单变量的概率分布。

```qsharp

newtype ContinuousDistribution = (Sample : (Unit => Double));
```



## <a name="named-items"></a>命名项

### <a name="sample--unit--double"></a>示例： [单元](xref:microsoft.quantum.lang-ref.unit) => [Double](xref:microsoft.quantum.lang-ref.double) 



## <a name="see-also"></a>另请参阅

- [ComplexDistribution。](xref:Microsoft.Quantum.Random.ComplexDistribution)
- [DiscreteDistribution。](xref:Microsoft.Quantum.Random.DiscreteDistribution)
- [BigDiscreteDistribution。](xref:Microsoft.Quantum.Random.BigDiscreteDistribution)