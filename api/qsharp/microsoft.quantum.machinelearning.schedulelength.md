---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854911"
---
# <a name="schedulelength-function"></a>ScheduleLength 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


返回给定抽样计划中的元素数。

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a>输入

### <a name="schedule--samplingschedule"></a>计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

要返回其长度的采样计划。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

给定采样计划中的元素数。