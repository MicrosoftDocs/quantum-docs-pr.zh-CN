---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701217"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="bc83f-102">TimeDependentSimulationAlgorithm 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="bc83f-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="bc83f-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bc83f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bc83f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc83f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc83f-105">表示依赖时间的模拟算法。</span><span class="sxs-lookup"><span data-stu-id="bc83f-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="bc83f-106">依赖于时间的模拟技术将 <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="bc83f-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="bc83f-107">用于某些时间间隔的单一时间演变。</span><span class="sxs-lookup"><span data-stu-id="bc83f-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

