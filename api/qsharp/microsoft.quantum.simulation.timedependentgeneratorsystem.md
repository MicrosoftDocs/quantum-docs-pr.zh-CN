---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: dbbbb2b67dcf191c74e593f61eb894192acb4d48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854733"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="e3fc9-102">TimeDependentGeneratorSystem 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="e3fc9-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="e3fc9-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e3fc9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e3fc9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3fc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3fc9-105">表示时间依赖于时间的 dynamical 生成器作为函数，时间与 dynamical 生成器的值相同。</span><span class="sxs-lookup"><span data-stu-id="e3fc9-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

