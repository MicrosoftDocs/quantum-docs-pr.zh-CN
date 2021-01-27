---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: EvolutionSchedule 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: 345374fb8105f0f892eaef3bd2da0f0fa239c065
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814249"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="35c8c-102">EvolutionSchedule 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="35c8c-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="35c8c-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="35c8c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="35c8c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35c8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35c8c-105">表示依赖时间的 dynamical 生成器。</span><span class="sxs-lookup"><span data-stu-id="35c8c-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="35c8c-106">`Double`参数是 $ [0，1] $ 中的一个计划。</span><span class="sxs-lookup"><span data-stu-id="35c8c-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

