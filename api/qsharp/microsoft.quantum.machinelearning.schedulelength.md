---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 77538984fbd7334712df423b991ef43ce31ed849
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700261"
---
# <a name="schedulelength-function"></a><span data-ttu-id="b3712-102">ScheduleLength 函数</span><span class="sxs-lookup"><span data-stu-id="b3712-102">ScheduleLength function</span></span>

<span data-ttu-id="b3712-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b3712-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b3712-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3712-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3712-105">返回给定抽样计划中的元素数。</span><span class="sxs-lookup"><span data-stu-id="b3712-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="b3712-106">输入</span><span class="sxs-lookup"><span data-stu-id="b3712-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="b3712-107">计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="b3712-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="b3712-108">要返回其长度的采样计划。</span><span class="sxs-lookup"><span data-stu-id="b3712-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="b3712-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3712-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3712-110">给定采样计划中的元素数。</span><span class="sxs-lookup"><span data-stu-id="b3712-110">The number of elements in the given sampling schedule.</span></span>