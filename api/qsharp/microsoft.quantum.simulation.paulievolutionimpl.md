---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: PauliEvolutionImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 2fc9fda2dd6eec71d8b17ba8a00d8545e517eec8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696678"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="2734e-102">PauliEvolutionImpl 操作</span><span class="sxs-lookup"><span data-stu-id="2734e-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="2734e-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2734e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2734e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2734e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2734e-105">将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="2734e-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="2734e-106">有关更多详细信息，请参阅 [Dynamical 生成器建模](/quantum/libraries/data-structures#dynamical-generator-modeling) 。</span><span class="sxs-lookup"><span data-stu-id="2734e-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2734e-107">输入</span><span class="sxs-lookup"><span data-stu-id="2734e-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="2734e-108">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2734e-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2734e-109">要在 Pauli 基础中表示为单一进化的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="2734e-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="2734e-110">delta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2734e-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2734e-111">中引用的术语在时间演变期间的乘数 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="2734e-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2734e-112">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2734e-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2734e-113">根据时间演化运算符进行注册。</span><span class="sxs-lookup"><span data-stu-id="2734e-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2734e-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2734e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

