---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 060f4e4f23bb8b47518a3a22bbca8ab0be6e13b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696677"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="4bea6-102">PauliEvolutionFunction 函数</span><span class="sxs-lookup"><span data-stu-id="4bea6-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="4bea6-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4bea6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4bea6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4bea6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4bea6-105">将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="4bea6-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="4bea6-106">输入</span><span class="sxs-lookup"><span data-stu-id="4bea6-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="4bea6-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4bea6-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4bea6-108">要在 Pauli 基础中表示为单一进化的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="4bea6-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="4bea6-109">输出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="4bea6-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="4bea6-110">， `EvolutionUnitary` 它表示 "generatorIndex" 中引用的术语的时间演变。</span><span class="sxs-lookup"><span data-stu-id="4bea6-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>