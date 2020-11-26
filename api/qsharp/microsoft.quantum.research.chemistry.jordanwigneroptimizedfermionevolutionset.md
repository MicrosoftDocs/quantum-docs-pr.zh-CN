---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 2cd555882792c29cb2ed71972739505df11fbabc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225731"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a><span data-ttu-id="e2057-102">JordanWignerOptimizedFermionEvolutionSet 函数</span><span class="sxs-lookup"><span data-stu-id="e2057-102">JordanWignerOptimizedFermionEvolutionSet function</span></span>

<span data-ttu-id="e2057-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e2057-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="e2057-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e2057-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="e2057-105">将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="e2057-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a><span data-ttu-id="e2057-106">输入</span><span class="sxs-lookup"><span data-stu-id="e2057-106">Input</span></span>

### <a name="parityqubit--qubit"></a><span data-ttu-id="e2057-107">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e2057-107">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e2057-108">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="e2057-108">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionset"></a><span data-ttu-id="e2057-109">输出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="e2057-109">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="e2057-110">一个 `EvolutionSet` ，它将 `GeneratorIndex` JWOptimized 基础的映射到 "EvolutionUnitary"。</span><span class="sxs-lookup"><span data-stu-id="e2057-110">An `EvolutionSet` that maps a `GeneratorIndex` for the JWOptimized basis to an \`EvolutionUnitary.</span></span>