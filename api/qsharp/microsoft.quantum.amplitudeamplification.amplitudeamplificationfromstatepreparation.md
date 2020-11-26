---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191595"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="eac0c-102">AmplitudeAmplificationFromStatePreparation 函数</span><span class="sxs-lookup"><span data-stu-id="eac0c-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="eac0c-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="eac0c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="eac0c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eac0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eac0c-105">用于部分反射的 oracles 放大幅度。</span><span class="sxs-lookup"><span data-stu-id="eac0c-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="eac0c-106">输入</span><span class="sxs-lookup"><span data-stu-id="eac0c-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="eac0c-107">阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="eac0c-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="eac0c-108">部分反射的阶段</span><span class="sxs-lookup"><span data-stu-id="eac0c-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="eac0c-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="eac0c-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="eac0c-110">准备开始状态的单一 oracle $A $</span><span class="sxs-lookup"><span data-stu-id="eac0c-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="eac0c-111">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eac0c-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eac0c-112">用于标记 qubit 的索引</span><span class="sxs-lookup"><span data-stu-id="eac0c-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="eac0c-113">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="eac0c-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="eac0c-114">实现由部分反射实现的 oracles 放大幅度的操作。</span><span class="sxs-lookup"><span data-stu-id="eac0c-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="eac0c-115">备注</span><span class="sxs-lookup"><span data-stu-id="eac0c-115">Remarks</span></span>

<span data-ttu-id="eac0c-116">这会在开始和目标状态的形式上强制实施更严格的条件，而不是在中 `AmpAmpByReflectionPhases` 。</span><span class="sxs-lookup"><span data-stu-id="eac0c-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="eac0c-117">假定目标状态标有 $ \ket {1} \_ f $。</span><span class="sxs-lookup"><span data-stu-id="eac0c-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="eac0c-118">假设在 {0} \_ 大多数情况下，\begin{align} A\ket {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 在 `flagQubit` `auxiliaryRegister` 状态 $ \ket {0} \_ {f} \ket {0} \_ s $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="eac0c-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>