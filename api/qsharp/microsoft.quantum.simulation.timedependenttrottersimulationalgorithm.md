---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696622"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="d91fd-102">TimeDependentTrotterSimulationAlgorithm 函数</span><span class="sxs-lookup"><span data-stu-id="d91fd-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="d91fd-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d91fd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d91fd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d91fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d91fd-105">`TimeDependentSimulationAlgorithm` 使用 Trotter – Suzuki 分解来估算求解依赖于时间的 Schrodinger 公式的单一运算符的函数。</span><span class="sxs-lookup"><span data-stu-id="d91fd-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="d91fd-106">输入</span><span class="sxs-lookup"><span data-stu-id="d91fd-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="d91fd-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d91fd-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d91fd-108">单个 Trotter 步骤中模拟时间演化的持续时间。</span><span class="sxs-lookup"><span data-stu-id="d91fd-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="d91fd-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d91fd-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d91fd-110">Trotter 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="d91fd-110">Order of Trotter integrator.</span></span> <span data-ttu-id="d91fd-111">此值必须是1或偶数。</span><span class="sxs-lookup"><span data-stu-id="d91fd-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="d91fd-112">输出： [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="d91fd-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="d91fd-113">`TimeDependentSimulationAlgorithm` 类型。</span><span class="sxs-lookup"><span data-stu-id="d91fd-113">A `TimeDependentSimulationAlgorithm` type.</span></span>