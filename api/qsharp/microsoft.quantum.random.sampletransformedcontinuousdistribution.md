---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: 62f6f4ff372143228de007c98a23697022fcfd24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856107"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a>SampleTransformedContinuousDistribution 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


从转换后的分发进行采样的仅限内部操作。
只应通过部分应用程序使用。

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a>输入

### <a name="transform--double---double"></a>转换： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)




### <a name="distribution--continuousdistribution"></a>分发： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)





## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

