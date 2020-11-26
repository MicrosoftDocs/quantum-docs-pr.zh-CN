---
uid: Microsoft.Quantum.Random.BigDiscreteDistribution
title: BigDiscreteDistribution 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: BigDiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers of arbitrary size.
ms.openlocfilehash: add39f057b209bb19336a2af3d08aefcf8e1e11e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193193"
---
# <a name="bigdiscretedistribution-user-defined-type"></a>BigDiscreteDistribution 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


表示针对任意大小的整数的单变量概率分布。

```qsharp

newtype BigDiscreteDistribution = (Sample : (Unit => BigInt));
```



## <a name="named-items"></a>命名项

### <a name="sample--unit--bigint"></a>示例： [单元](xref:microsoft.quantum.lang-ref.unit) => [BigInt](xref:microsoft.quantum.lang-ref.bigint) 



## <a name="see-also"></a>另请参阅

- [ContinuousDistribution。](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [ComplexDistribution。](xref:Microsoft.Quantum.Random.ComplexDistribution)
- [DiscreteDistribution。](xref:Microsoft.Quantum.Random.DiscreteDistribution)