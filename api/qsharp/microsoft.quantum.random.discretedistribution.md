---
uid: Microsoft.Quantum.Random.DiscreteDistribution
title: DiscreteDistribution 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers.
ms.openlocfilehash: 5e0204f2eb7aa44451a049ad3d291487d468c52a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696696"
---
# <a name="discretedistribution-user-defined-type"></a>DiscreteDistribution 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


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