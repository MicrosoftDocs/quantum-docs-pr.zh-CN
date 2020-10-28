---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700132"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="97a7a-102">AmplitudeAmplificationFromPartialReflections 函数</span><span class="sxs-lookup"><span data-stu-id="97a7a-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="97a7a-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="97a7a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="97a7a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97a7a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97a7a-105">通过部分反射放大幅度。</span><span class="sxs-lookup"><span data-stu-id="97a7a-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="97a7a-106">输入</span><span class="sxs-lookup"><span data-stu-id="97a7a-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="97a7a-107">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="97a7a-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="97a7a-108">部分反射的阶段</span><span class="sxs-lookup"><span data-stu-id="97a7a-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="97a7a-109">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="97a7a-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="97a7a-110">关于开始状态的反射运算符</span><span class="sxs-lookup"><span data-stu-id="97a7a-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="97a7a-111">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="97a7a-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="97a7a-112">有关目标状态的反射运算符</span><span class="sxs-lookup"><span data-stu-id="97a7a-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="97a7a-113">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="97a7a-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="97a7a-114">通过部分反射实现波幅放大的操作。</span><span class="sxs-lookup"><span data-stu-id="97a7a-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="97a7a-115">注解</span><span class="sxs-lookup"><span data-stu-id="97a7a-115">Remarks</span></span>

<span data-ttu-id="97a7a-116">振幅放大是一种特殊的在意波幅放大，其中没有系统 qubits，而在意 oracle 设置为 identity。</span><span class="sxs-lookup"><span data-stu-id="97a7a-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="97a7a-117">在大多数情况下， `startQubits` 在状态 $ \ket{\text{start}} $1 中初始化， \_ 后者是的 $-$1 eigenstate `startStateReflection` 。</span><span class="sxs-lookup"><span data-stu-id="97a7a-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>