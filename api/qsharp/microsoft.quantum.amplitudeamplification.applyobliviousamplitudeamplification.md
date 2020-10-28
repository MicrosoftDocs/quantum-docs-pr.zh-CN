---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700112"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="09fcc-102">ApplyObliviousAmplitudeAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="09fcc-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="09fcc-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="09fcc-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="09fcc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09fcc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09fcc-105">通过指定部分反射来在意波幅放大。</span><span class="sxs-lookup"><span data-stu-id="09fcc-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="09fcc-106">输入</span><span class="sxs-lookup"><span data-stu-id="09fcc-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="09fcc-107">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="09fcc-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="09fcc-108">部分反射的阶段</span><span class="sxs-lookup"><span data-stu-id="09fcc-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="09fcc-109">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="09fcc-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="09fcc-110">有关辅助寄存器开始状态的反射运算符</span><span class="sxs-lookup"><span data-stu-id="09fcc-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="09fcc-111">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="09fcc-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="09fcc-112">有关辅助寄存器的目标状态的反射运算符</span><span class="sxs-lookup"><span data-stu-id="09fcc-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="09fcc-113">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="09fcc-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="09fcc-114">单一 oracle $O 类型 `ObliviousOracle` ，它在辅助和系统寄存器上共同操作。</span><span class="sxs-lookup"><span data-stu-id="09fcc-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="09fcc-115">auxiliaryRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="09fcc-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="09fcc-116">辅助寄存器</span><span class="sxs-lookup"><span data-stu-id="09fcc-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="09fcc-117">systemRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="09fcc-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="09fcc-118">系统注册</span><span class="sxs-lookup"><span data-stu-id="09fcc-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="09fcc-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09fcc-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="09fcc-120">注解</span><span class="sxs-lookup"><span data-stu-id="09fcc-120">Remarks</span></span>

<span data-ttu-id="09fcc-121">在给定的特定辅助启动状态 $ \ket{\text{start}} $ \_ 、特定辅助目标状态 $ \ket{\text{target}} \_ a $ 和任何系统状态 $ \ket{\psi} \_ s $ 中，假设 \begin{align} O\ket {\ text {start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{target} ^ \perp} a\cdots \end{align} \_ 用于某些单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="09fcc-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="09fcc-122">通过一系列反射，可以反映辅助寄存器上的起始和目标状态 `signalOracle` 以及其 adjoint 的应用程序，因此可能会更改应用 U 的成功概率。</span><span class="sxs-lookup"><span data-stu-id="09fcc-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="09fcc-123">在大多数情况下， `auxiliaryRegister` 在状态 $ \ket{\text{start}} 中进行初始化 \_ 。</span><span class="sxs-lookup"><span data-stu-id="09fcc-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="09fcc-124">参考</span><span class="sxs-lookup"><span data-stu-id="09fcc-124">References</span></span>

<span data-ttu-id="09fcc-125">查看</span><span class="sxs-lookup"><span data-stu-id="09fcc-125">See</span></span>

- <span data-ttu-id="09fcc-126">[ *D.W. Berry，am Childs，Cleve，Kothari，R.D. Somma，*](https://arxiv.org/abs/1312.1414) 适用于标准版。</span><span class="sxs-lookup"><span data-stu-id="09fcc-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="09fcc-127">查看</span><span class="sxs-lookup"><span data-stu-id="09fcc-127">See</span></span>
- <span data-ttu-id="09fcc-128">[ *G.H. Low、I.L. 语*](https://arxiv.org/abs/1610.06546) for 通用化 to partial 反射。</span><span class="sxs-lookup"><span data-stu-id="09fcc-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>