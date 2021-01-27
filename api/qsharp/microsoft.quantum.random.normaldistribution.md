---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814189"
---
# <a name="normaldistribution-function"></a>NormalDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回具有给定平均值和方差的正态分布。

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>输入

### <a name="mean--double"></a>均值： [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>变体： [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>示例

下面的示例从正态分布（2和标准偏差为0.1）中提取了10个样本：

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>另请参阅

- [StandardNormalDistribution。](xref:Microsoft.Quantum.Random.StandardNormalDistribution)