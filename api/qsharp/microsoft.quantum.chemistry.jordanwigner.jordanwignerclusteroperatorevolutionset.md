---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorEvolutionSet
title: JordanWignerClusterOperatorEvolutionSet 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 81a2a109be0b19da5aa0a3feca76966deabeb665
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695755"
---
# <a name="jordanwignerclusteroperatorevolutionset-function"></a><span data-ttu-id="3033e-102">JordanWignerClusterOperatorEvolutionSet 函数</span><span class="sxs-lookup"><span data-stu-id="3033e-102">JordanWignerClusterOperatorEvolutionSet function</span></span>

<span data-ttu-id="3033e-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3033e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3033e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3033e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3033e-105">将 dynamical 生成器表示为一组 simulatable 入口和 JordanWigner 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="3033e-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerClusterOperatorEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="3033e-106">输出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="3033e-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="3033e-107">一个 `EvolutionSet` ，它将 `GeneratorIndex` JordanWigner 基础的映射到 "EvolutionUnitary"。</span><span class="sxs-lookup"><span data-stu-id="3033e-107">An `EvolutionSet` that maps a `GeneratorIndex` for the JordanWigner basis to an \`EvolutionUnitary.</span></span>