---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700097"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="e20bd-102">ObliviousAmplitudeAmplificationFromStatePreparation 函数</span><span class="sxs-lookup"><span data-stu-id="e20bd-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="e20bd-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e20bd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e20bd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e20bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e20bd-105">用于部分反射的在意波幅按 oracles 放大。</span><span class="sxs-lookup"><span data-stu-id="e20bd-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e20bd-106">输入</span><span class="sxs-lookup"><span data-stu-id="e20bd-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="e20bd-107">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="e20bd-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="e20bd-108">部分反射的阶段</span><span class="sxs-lookup"><span data-stu-id="e20bd-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="e20bd-109">startStateOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="e20bd-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="e20bd-110">准备辅助启动状态的单一 oracle $A $</span><span class="sxs-lookup"><span data-stu-id="e20bd-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="e20bd-111">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="e20bd-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="e20bd-112">单一 oracle $O 类型 `ObliviousOracle` ，它在辅助和系统寄存器上共同操作</span><span class="sxs-lookup"><span data-stu-id="e20bd-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="e20bd-113">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e20bd-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e20bd-114">Qubit 标志注册的索引</span><span class="sxs-lookup"><span data-stu-id="e20bd-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="e20bd-115">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="e20bd-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e20bd-116">基于部分反射实现在意波幅放大的操作。</span><span class="sxs-lookup"><span data-stu-id="e20bd-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="e20bd-117">注解</span><span class="sxs-lookup"><span data-stu-id="e20bd-117">Remarks</span></span>

<span data-ttu-id="e20bd-118">这会对辅助启动和目标状态的形式施加更严格的条件，而不是在中 `AmpAmpObliviousByReflectionPhases` 。</span><span class="sxs-lookup"><span data-stu-id="e20bd-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="e20bd-119">假定 $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{start}} \_ {fa} $ 为 \_ 计算基础 $ \ket {0} \_ f\ket $ 准备辅助开始状态 $ \ket{\text{start}} {fa} $ {0} 。</span><span class="sxs-lookup"><span data-stu-id="e20bd-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="e20bd-120">假定目标状态标有 $ \ket {1} \_ f $。</span><span class="sxs-lookup"><span data-stu-id="e20bd-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="e20bd-121">假设 \begin{align} O\ket {\ text {start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {任何}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 用于某些单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="e20bd-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>