---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: 采样函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700268"
---
# <a name="sampled-function"></a>采样函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


使用给定的计划来采集给定数组的示例。

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="schedule--samplingschedule"></a>计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

用于采样值的计划。


### <a name="values--t"></a>值： t []

要取样的值数组。



## <a name="output--t"></a>输出： t []

按给定计划后的值的元素数组。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

