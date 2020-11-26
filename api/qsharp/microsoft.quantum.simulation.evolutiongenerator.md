---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 9e0fc5a232070c238aad943ab73f064999237c15
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229437"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="b84e5-102">EvolutionGenerator 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="b84e5-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="b84e5-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b84e5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b84e5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b84e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b84e5-105">将 dynamical 生成器表示为一组 simulatable 入口，并以这种方式进行扩展。</span><span class="sxs-lookup"><span data-stu-id="b84e5-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="b84e5-106">字词数的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="b84e5-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

