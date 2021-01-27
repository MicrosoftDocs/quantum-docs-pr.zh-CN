---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: c171021272076cc3960307523e25c4493bb49c5a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845871"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="759b7-102">ApplyObliviousAmplitudeAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="759b7-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="759b7-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="759b7-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="759b7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="759b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="759b7-105">通过指定部分反射来在意波幅放大。</span><span class="sxs-lookup"><span data-stu-id="759b7-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="759b7-106">输入</span><span class="sxs-lookup"><span data-stu-id="759b7-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="759b7-107">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="759b7-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="759b7-108">部分反射的阶段</span><span class="sxs-lookup"><span data-stu-id="759b7-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="759b7-109">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="759b7-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="759b7-110">有关辅助寄存器开始状态的反射运算符</span><span class="sxs-lookup"><span data-stu-id="759b7-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="759b7-111">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="759b7-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="759b7-112">有关辅助寄存器的目标状态的反射运算符</span><span class="sxs-lookup"><span data-stu-id="759b7-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="759b7-113">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="759b7-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="759b7-114">单一 oracle $O 类型 `ObliviousOracle` ，它在辅助和系统寄存器上共同操作。</span><span class="sxs-lookup"><span data-stu-id="759b7-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="759b7-115">auxiliaryRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="759b7-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="759b7-116">辅助寄存器</span><span class="sxs-lookup"><span data-stu-id="759b7-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="759b7-117">systemRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="759b7-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="759b7-118">系统注册</span><span class="sxs-lookup"><span data-stu-id="759b7-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="759b7-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="759b7-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="759b7-120">备注</span><span class="sxs-lookup"><span data-stu-id="759b7-120">Remarks</span></span>

<span data-ttu-id="759b7-121">在给定的特定辅助启动状态 $ \ket{\text{start}} $ \_ 、特定辅助目标状态 $ \ket{\text{target}} \_ a $ 和任何系统状态 $ \ket{\psi} \_ s $ 中，假设 \begin{align} O\ket {\ text {start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{target} ^ \perp} a\cdots \end{align} \_ 用于某些单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="759b7-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="759b7-122">通过一系列反射，可以反映辅助寄存器上的起始和目标状态 `signalOracle` 以及其 adjoint 的应用程序，因此可能会更改应用 U 的成功概率。</span><span class="sxs-lookup"><span data-stu-id="759b7-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="759b7-123">在大多数情况下， `auxiliaryRegister` 在状态 $ \ket{\text{start}} 中进行初始化 \_ 。</span><span class="sxs-lookup"><span data-stu-id="759b7-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="759b7-124">参考</span><span class="sxs-lookup"><span data-stu-id="759b7-124">References</span></span>

<span data-ttu-id="759b7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="759b7-125">See</span></span>

- <span data-ttu-id="759b7-126">[ *D.W. Berry，am Childs，Cleve，Kothari，R.D. Somma，*](https://arxiv.org/abs/1312.1414) 适用于标准版。</span><span class="sxs-lookup"><span data-stu-id="759b7-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="759b7-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="759b7-127">See</span></span>
- <span data-ttu-id="759b7-128">[ *G.H. Low、I.L. 语*](https://arxiv.org/abs/1610.06546) for 通用化 to partial 反射。</span><span class="sxs-lookup"><span data-stu-id="759b7-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>