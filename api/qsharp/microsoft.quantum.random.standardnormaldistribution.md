---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: StandardNormalDistribution 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857799"
---
# <a name="standardnormaldistribution-function"></a>StandardNormalDistribution 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回一个平均分布，其平均值为0，方差为1。

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a>输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>示例

下面从标准正态分布绘制了10个样本：

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a>另请参阅

- [NormalDistribution。](xref:Microsoft.Quantum.Random.NormalDistribution)