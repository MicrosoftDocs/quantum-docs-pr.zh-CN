---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700689"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="0c9cf-102">GeneratorIndex 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="0c9cf-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="0c9cf-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0c9cf-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0c9cf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c9cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c9cf-105">表示所有 dynamical 生成器（如 Hermitian 运算符）集中的单个基元术语，该生成器存在一个从该生成器到该生成器的时间演化的映射 `EvolutionSet` 。</span><span class="sxs-lookup"><span data-stu-id="0c9cf-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="0c9cf-106">第一个元素 (Int []，Double [] ) 是单个字词的索引，例如，系数为0.5 的 Pauli 字符串 XXY 将按 ( [1，1，2]，[0.5] ) 进行索引。</span><span class="sxs-lookup"><span data-stu-id="0c9cf-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="0c9cf-107">另外，可以通过 ( []、[φ] ) 以连续变量（例如 X cos φ + Y sin φ）表示的 Hamiltonians。</span><span class="sxs-lookup"><span data-stu-id="0c9cf-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="0c9cf-108">第二个元素对生成器在其上操作的子系统进行索引。</span><span class="sxs-lookup"><span data-stu-id="0c9cf-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="0c9cf-109">注解</span><span class="sxs-lookup"><span data-stu-id="0c9cf-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0c9cf-110">`GeneratorIndex`除引用一组特定生成器外，未定义的解释。</span><span class="sxs-lookup"><span data-stu-id="0c9cf-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c9cf-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c9cf-111">See Also</span></span>

- [<span data-ttu-id="0c9cf-112">EvolutionSet。</span><span class="sxs-lookup"><span data-stu-id="0c9cf-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="0c9cf-113">PauliEvolutionSet。</span><span class="sxs-lookup"><span data-stu-id="0c9cf-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)