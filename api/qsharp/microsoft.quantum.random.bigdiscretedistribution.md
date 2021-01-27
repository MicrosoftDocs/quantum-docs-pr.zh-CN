---
uid: Microsoft.Quantum.Random.BigDiscreteDistribution
title: BigDiscreteDistribution 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: BigDiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers of arbitrary size.
ms.openlocfilehash: de33b458b63a8c1f2c4af28dbb7db0b97367ce98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855794"
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