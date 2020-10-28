---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: JordanWignerFermionImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 616174d4d7f5ac8f4cea9454098d819468076648
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695745"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="b35aa-102">JordanWignerFermionImpl 操作</span><span class="sxs-lookup"><span data-stu-id="b35aa-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="b35aa-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b35aa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b35aa-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b35aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b35aa-105">将 dynamical 生成器表示为一组 simulatable 入口和 JordanWigner 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="b35aa-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="b35aa-106">有关更多详细信息，请参阅 [Dynamical 生成器建模](../libraries/data-structures#dynamical-generator-modeling) 。</span><span class="sxs-lookup"><span data-stu-id="b35aa-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b35aa-107">输入</span><span class="sxs-lookup"><span data-stu-id="b35aa-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="b35aa-108">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b35aa-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b35aa-109">要在 JordanWigner 中表示为单一演变的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="b35aa-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="b35aa-110">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b35aa-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b35aa-111">中引用的术语在时间演变期间的乘数 `generatorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="b35aa-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b35aa-112">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b35aa-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b35aa-113">根据时间演化运算符进行注册。</span><span class="sxs-lookup"><span data-stu-id="b35aa-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b35aa-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b35aa-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

