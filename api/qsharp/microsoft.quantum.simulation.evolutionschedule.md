---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: EvolutionSchedule 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: f99c72a44acc3fdcd9c0f182b51d9437b5e6606d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225289"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="948b0-102">EvolutionSchedule 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="948b0-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="948b0-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="948b0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="948b0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="948b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="948b0-105">表示依赖时间的 dynamical 生成器。</span><span class="sxs-lookup"><span data-stu-id="948b0-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="948b0-106">`Double`参数是 $ [0，1] $ 中的一个计划。</span><span class="sxs-lookup"><span data-stu-id="948b0-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

