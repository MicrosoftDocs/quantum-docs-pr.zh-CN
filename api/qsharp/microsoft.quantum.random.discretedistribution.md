---
uid: Microsoft.Quantum.Random.DiscreteDistribution
title: DiscreteDistribution 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers.
ms.openlocfilehash: d492c86a6d72144695e1d0c2a94e8fe64cf1d3ef
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193040"
---
# <a name="discretedistribution-user-defined-type"></a>DiscreteDistribution 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


表示单变量的概率分布。

```qsharp

newtype DiscreteDistribution = (Sample : (Unit => Int));
```



## <a name="named-items"></a>命名项

### <a name="sample--unit--int"></a>示例： [单元](xref:microsoft.quantum.lang-ref.unit) => [Int](xref:microsoft.quantum.lang-ref.int) 



## <a name="see-also"></a>另请参阅

- [ContinuousDistribution。](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [ComplexDistribution。](xref:Microsoft.Quantum.Random.ComplexDistribution)
- [BigDiscreteDistribution。](xref:Microsoft.Quantum.Random.BigDiscreteDistribution)