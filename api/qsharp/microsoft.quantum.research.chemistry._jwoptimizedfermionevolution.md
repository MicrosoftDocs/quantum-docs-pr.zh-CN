---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: _JWOptimizedFermionEvolution 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 670accb6288d26cc7deb89c8d580fe082e795d57
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226003"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="5a579-102">_JWOptimizedFermionEvolution 操作</span><span class="sxs-lookup"><span data-stu-id="5a579-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="5a579-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5a579-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="5a579-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5a579-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="5a579-105">将 dynamical 生成器表示为一组 simulatable 入口和 JWOptimized 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="5a579-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="5a579-106">有关更多详细信息，请参阅 [Dynamical 生成器建模](../libraries/data-structures#dynamical-generator-modeling) 。</span><span class="sxs-lookup"><span data-stu-id="5a579-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a579-107">输入</span><span class="sxs-lookup"><span data-stu-id="5a579-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="5a579-108">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5a579-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5a579-109">要在 JWOptimized 基础中表示为单一进化的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="5a579-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5a579-110">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5a579-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5a579-111">中引用的术语在时间演变期间的乘数 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="5a579-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="5a579-112">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5a579-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5a579-113">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="5a579-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5a579-114">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5a579-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5a579-115">根据时间演化运算符进行注册。</span><span class="sxs-lookup"><span data-stu-id="5a579-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a579-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a579-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

