---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700125"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="b3feb-102">ApplyAmplitudeAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="b3feb-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="b3feb-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b3feb-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b3feb-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3feb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3feb-105">在给定寄存器上应用振幅放大，使用一组给定的阶段和 oracles 来反映初始状态和最终状态。</span><span class="sxs-lookup"><span data-stu-id="b3feb-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b3feb-106">输入</span><span class="sxs-lookup"><span data-stu-id="b3feb-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="b3feb-107">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b3feb-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b3feb-108">描述振幅放大算法的每个步骤中的部分反射的一组阶段。</span><span class="sxs-lookup"><span data-stu-id="b3feb-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="b3feb-109">有关示例，请参见 @"microsoft.quantum.amplitudeamplification.standardreflectionphases"。</span><span class="sxs-lookup"><span data-stu-id="b3feb-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="b3feb-110">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b3feb-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b3feb-111">反映初始状态的 oracle。</span><span class="sxs-lookup"><span data-stu-id="b3feb-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="b3feb-112">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b3feb-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b3feb-113">反映所需最终状态的 oracle。</span><span class="sxs-lookup"><span data-stu-id="b3feb-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b3feb-114">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b3feb-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b3feb-115">要对其执行振幅放大的寄存器。</span><span class="sxs-lookup"><span data-stu-id="b3feb-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b3feb-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3feb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
