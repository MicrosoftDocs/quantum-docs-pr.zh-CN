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
# <a name="sampled-function"></a><span data-ttu-id="63ba2-102">采样函数</span><span class="sxs-lookup"><span data-stu-id="63ba2-102">Sampled function</span></span>

<span data-ttu-id="63ba2-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="63ba2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="63ba2-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="63ba2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="63ba2-105">使用给定的计划来采集给定数组的示例。</span><span class="sxs-lookup"><span data-stu-id="63ba2-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="63ba2-106">输入</span><span class="sxs-lookup"><span data-stu-id="63ba2-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="63ba2-107">计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="63ba2-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="63ba2-108">用于采样值的计划。</span><span class="sxs-lookup"><span data-stu-id="63ba2-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="63ba2-109">值： t []</span><span class="sxs-lookup"><span data-stu-id="63ba2-109">values : 'T[]</span></span>

<span data-ttu-id="63ba2-110">要取样的值数组。</span><span class="sxs-lookup"><span data-stu-id="63ba2-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="63ba2-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="63ba2-111">Output : 'T[]</span></span>

<span data-ttu-id="63ba2-112">按给定计划后的值的元素数组。</span><span class="sxs-lookup"><span data-stu-id="63ba2-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63ba2-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="63ba2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63ba2-114">找</span><span class="sxs-lookup"><span data-stu-id="63ba2-114">'T</span></span>

