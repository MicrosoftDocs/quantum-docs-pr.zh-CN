---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: fb53b90b6ab5ce1003f66b68a8c2ad8b3631f627
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230338"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="54aa1-102">PauliEvolutionSet 函数</span><span class="sxs-lookup"><span data-stu-id="54aa1-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="54aa1-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="54aa1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="54aa1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54aa1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54aa1-105">将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="54aa1-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="54aa1-106">输出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="54aa1-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="54aa1-107">一个 `EvolutionSet` ，它将 `GeneratorIndex` Pauli 基础的映射到 "EvolutionUnitary"。</span><span class="sxs-lookup"><span data-stu-id="54aa1-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="54aa1-108">备注</span><span class="sxs-lookup"><span data-stu-id="54aa1-108">Remarks</span></span>

<span data-ttu-id="54aa1-109">这是由的部分应用程序获取的 <xref:microsoft.quantum.simulation.paulievolutionfunction> 。</span><span class="sxs-lookup"><span data-stu-id="54aa1-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>