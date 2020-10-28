---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: EvolutionSchedule 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: 4dc8bf4028e82d3e746779ae8c7d400dcbd3ea1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695261"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="d58cd-102">EvolutionSchedule 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="d58cd-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="d58cd-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d58cd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d58cd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d58cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d58cd-105">表示依赖时间的 dynamical 生成器。</span><span class="sxs-lookup"><span data-stu-id="d58cd-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="d58cd-106">`Double`参数是 $ [0，1] $ 中的一个计划。</span><span class="sxs-lookup"><span data-stu-id="d58cd-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

