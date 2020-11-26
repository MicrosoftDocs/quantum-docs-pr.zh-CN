---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 008bdcdc0a7c0ad2775dea65ebba46556092beed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211587"
---
# <a name="schedulelength-function"></a><span data-ttu-id="f5bd0-102">ScheduleLength 函数</span><span class="sxs-lookup"><span data-stu-id="f5bd0-102">ScheduleLength function</span></span>

<span data-ttu-id="f5bd0-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f5bd0-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f5bd0-105">返回给定抽样计划中的元素数。</span><span class="sxs-lookup"><span data-stu-id="f5bd0-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="f5bd0-106">输入</span><span class="sxs-lookup"><span data-stu-id="f5bd0-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="f5bd0-107">计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="f5bd0-108">要返回其长度的采样计划。</span><span class="sxs-lookup"><span data-stu-id="f5bd0-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="f5bd0-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5bd0-110">给定采样计划中的元素数。</span><span class="sxs-lookup"><span data-stu-id="f5bd0-110">The number of elements in the given sampling schedule.</span></span>