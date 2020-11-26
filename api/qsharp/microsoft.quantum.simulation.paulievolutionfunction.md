---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: e581cd4d0a3caf96bece9979a1d850aad7842727
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230348"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="cb68c-102">PauliEvolutionFunction 函数</span><span class="sxs-lookup"><span data-stu-id="cb68c-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="cb68c-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cb68c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cb68c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb68c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb68c-105">将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="cb68c-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="cb68c-106">输入</span><span class="sxs-lookup"><span data-stu-id="cb68c-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="cb68c-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cb68c-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cb68c-108">要在 Pauli 基础中表示为单一进化的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="cb68c-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="cb68c-109">输出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="cb68c-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="cb68c-110">， `EvolutionUnitary` 它表示 "generatorIndex" 中引用的术语的时间演变。</span><span class="sxs-lookup"><span data-stu-id="cb68c-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>