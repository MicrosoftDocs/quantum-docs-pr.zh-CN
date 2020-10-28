---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695260"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="f1a9d-102">EvolutionSet 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="f1a9d-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="f1a9d-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f1a9d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f1a9d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1a9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1a9d-105">表示一组可随时实现和用于实现模拟算法的入口。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="f1a9d-106">集中的元素由进行索引  <xref:microsoft.quantum.simulation.generatorindex> ，每个集由到的函数描述 `GeneratorIndex`  <xref:microsoft.quantum.simulation.evolutionunitary> ，这些操作由表示时间的实数参数化</span><span class="sxs-lookup"><span data-stu-id="f1a9d-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

