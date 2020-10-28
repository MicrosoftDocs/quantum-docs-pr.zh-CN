---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: 144a44448c9fda7a038b17ac7c49f63e8cc4dd55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696623"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="40b65-102">TimeDependentGeneratorSystem 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="40b65-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="40b65-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="40b65-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="40b65-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40b65-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="40b65-105">表示时间依赖于时间的 dynamical 生成器作为函数，时间与 dynamical 生成器的值相同。</span><span class="sxs-lookup"><span data-stu-id="40b65-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

