---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225595"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="03818-102">_IdentityTimeDependentGeneratorSystem 函数</span><span class="sxs-lookup"><span data-stu-id="03818-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="03818-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="03818-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="03818-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03818-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03818-105">返回与 Hamiltonian 一致的生成器系统 `H(s) = 0` ，其中 `s` 为 schedule 参数。</span><span class="sxs-lookup"><span data-stu-id="03818-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="03818-106">输入</span><span class="sxs-lookup"><span data-stu-id="03818-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="03818-107">计划： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="03818-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="03818-108">此输入将被忽略，并定义为与 <xref:microsoft.quantum.canon.timedependentgeneratorsystem> 用户定义的类型保持一致。</span><span class="sxs-lookup"><span data-stu-id="03818-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="03818-109">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="03818-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="03818-110">对于所有 $s $，在 Hamiltonian $H (s) = $0 下表示演化的生成器系统。</span><span class="sxs-lookup"><span data-stu-id="03818-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>