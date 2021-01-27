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
# <a name="schedulelength-function"></a><span data-ttu-id="dd494-102">ScheduleLength 函数</span><span class="sxs-lookup"><span data-stu-id="dd494-102">ScheduleLength function</span></span>

<span data-ttu-id="dd494-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dd494-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dd494-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dd494-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="dd494-105">返回给定抽样计划中的元素数。</span><span class="sxs-lookup"><span data-stu-id="dd494-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="dd494-106">输入</span><span class="sxs-lookup"><span data-stu-id="dd494-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="dd494-107">计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="dd494-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="dd494-108">要返回其长度的采样计划。</span><span class="sxs-lookup"><span data-stu-id="dd494-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="dd494-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd494-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd494-110">给定采样计划中的元素数。</span><span class="sxs-lookup"><span data-stu-id="dd494-110">The number of elements in the given sampling schedule.</span></span>