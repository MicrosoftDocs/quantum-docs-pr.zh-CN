---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696621"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="3ad4f-102">TrotterSimulationAlgorithm 函数</span><span class="sxs-lookup"><span data-stu-id="3ad4f-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="3ad4f-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3ad4f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3ad4f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ad4f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ad4f-105">`SimulationAlgorithm` 使用 Trotter – Suzuki 分解来近似于时间演化运算符 _exp (-iHt)_ 的函数。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="3ad4f-106">输入</span><span class="sxs-lookup"><span data-stu-id="3ad4f-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="3ad4f-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ad4f-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ad4f-108">单个 Trotter 步骤中模拟时间演化的持续时间。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="3ad4f-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ad4f-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ad4f-110">Trotter 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-110">Order of Trotter integrator.</span></span> <span data-ttu-id="3ad4f-111">此值必须是1或偶数。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="3ad4f-112">输出： [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="3ad4f-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="3ad4f-113">`SimulationAlgorithm` 类型。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-113">A `SimulationAlgorithm` type.</span></span>