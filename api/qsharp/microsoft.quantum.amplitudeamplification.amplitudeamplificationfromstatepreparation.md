---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700129"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="9da22-102">AmplitudeAmplificationFromStatePreparation 函数</span><span class="sxs-lookup"><span data-stu-id="9da22-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="9da22-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="9da22-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="9da22-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9da22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9da22-105">用于部分反射的 oracles 放大幅度。</span><span class="sxs-lookup"><span data-stu-id="9da22-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9da22-106">输入</span><span class="sxs-lookup"><span data-stu-id="9da22-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="9da22-107">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="9da22-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="9da22-108">部分反射的阶段</span><span class="sxs-lookup"><span data-stu-id="9da22-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="9da22-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="9da22-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="9da22-110">准备开始状态的单一 oracle $A $</span><span class="sxs-lookup"><span data-stu-id="9da22-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="9da22-111">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9da22-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9da22-112">用于标记 qubit 的索引</span><span class="sxs-lookup"><span data-stu-id="9da22-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="9da22-113">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9da22-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9da22-114">实现由部分反射实现的 oracles 放大幅度的操作。</span><span class="sxs-lookup"><span data-stu-id="9da22-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="9da22-115">注解</span><span class="sxs-lookup"><span data-stu-id="9da22-115">Remarks</span></span>

<span data-ttu-id="9da22-116">这会在开始和目标状态的形式上强制实施更严格的条件，而不是在中 `AmpAmpByReflectionPhases` 。</span><span class="sxs-lookup"><span data-stu-id="9da22-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="9da22-117">假定目标状态标有 $ \ket {1} \_ f $。</span><span class="sxs-lookup"><span data-stu-id="9da22-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="9da22-118">假设在 {0} \_ 大多数情况下，\begin{align} A\ket {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 在 `flagQubit` `auxiliaryRegister` 状态 $ \ket {0} \_ {f} \ket {0} \_ s $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="9da22-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>