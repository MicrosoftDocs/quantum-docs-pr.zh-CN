---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: be741216bf99305bf5f1d149c815e98aba36aad1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695263"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="432b9-102">EvolutionGenerator 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="432b9-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="432b9-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="432b9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="432b9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="432b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="432b9-105">将 dynamical 生成器表示为一组 simulatable 入口，并以这种方式进行扩展。</span><span class="sxs-lookup"><span data-stu-id="432b9-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="432b9-106">字词数的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="432b9-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

