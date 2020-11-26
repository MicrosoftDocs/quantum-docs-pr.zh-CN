---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: 采样函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211621"
---
# <a name="sampled-function"></a>采样函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

