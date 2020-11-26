---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 40a4bccc6cf74a63c354bfd628baa45768916fe2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229913"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="bae45-102">JWOptimizedFermionEvolutionFunction 函数</span><span class="sxs-lookup"><span data-stu-id="bae45-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="bae45-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bae45-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="bae45-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bae45-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="bae45-105">将 dynamical 生成器表示为一组 simulatable 入口和 JWOptimized 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="bae45-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="bae45-106">输入</span><span class="sxs-lookup"><span data-stu-id="bae45-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="bae45-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bae45-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bae45-108">要在 JWOptimized 基础中表示为单一进化的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="bae45-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="bae45-109">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bae45-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bae45-110">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="bae45-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="bae45-111">输出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="bae45-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="bae45-112">， `EvolutionUnitary` 它表示 "generatorIndex" 中引用的术语的时间演变。</span><span class="sxs-lookup"><span data-stu-id="bae45-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>