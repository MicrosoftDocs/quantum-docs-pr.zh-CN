---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: 采样函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854949"
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

