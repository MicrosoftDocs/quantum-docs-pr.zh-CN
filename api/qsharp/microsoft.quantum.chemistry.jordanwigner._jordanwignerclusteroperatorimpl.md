---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: _JordanWignerClusterOperatorImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 9507558ebe73bce87d9089aad22b94c1d9d579d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695830"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a><span data-ttu-id="2776c-102">_JordanWignerClusterOperatorImpl 操作</span><span class="sxs-lookup"><span data-stu-id="2776c-102">_JordanWignerClusterOperatorImpl operation</span></span>

<span data-ttu-id="2776c-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2776c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2776c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2776c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2776c-105">将 dynamical 生成器表示为一组 simulatable 入口和 JordanWigner 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="2776c-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="2776c-106">有关更多详细信息，请参阅 [Dynamical 生成器建模](../libraries/data-structures#dynamical-generator-modeling) 。</span><span class="sxs-lookup"><span data-stu-id="2776c-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2776c-107">输入</span><span class="sxs-lookup"><span data-stu-id="2776c-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="2776c-108">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2776c-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2776c-109">要在 JordanWigner 中表示为单一演变的生成器索引。</span><span class="sxs-lookup"><span data-stu-id="2776c-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="2776c-110">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2776c-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2776c-111">与模拟算法的签名相匹配的虚拟变量。</span><span class="sxs-lookup"><span data-stu-id="2776c-111">Dummy variable to match signature of simulation algorithms.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2776c-112">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2776c-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2776c-113">根据时间演化运算符进行注册。</span><span class="sxs-lookup"><span data-stu-id="2776c-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2776c-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2776c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

