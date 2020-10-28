---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: _JordanWignerClusterOperatorFunction 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 58b0c7ad2216b1f58b9ea2765494b85fab4e1ff9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695838"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a><span data-ttu-id="fe499-102">_JordanWignerClusterOperatorFunction 函数</span><span class="sxs-lookup"><span data-stu-id="fe499-102">_JordanWignerClusterOperatorFunction function</span></span>

<span data-ttu-id="fe499-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="fe499-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="fe499-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe499-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe499-105">将 dynamical 生成器表示为一组 simulatable 入口和 JordanWigner 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="fe499-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="fe499-106">输入</span><span class="sxs-lookup"><span data-stu-id="fe499-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="fe499-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fe499-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fe499-108">要在 JordanWigner 中表示为单一演变的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="fe499-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="fe499-109">输出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="fe499-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="fe499-110">， `EvolutionUnitary` 它表示 "generatorIndex" 中引用的术语的时间演变。</span><span class="sxs-lookup"><span data-stu-id="fe499-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>