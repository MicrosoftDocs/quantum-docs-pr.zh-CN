---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843890"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="e20f6-102">TargetStateReflectionOracle 函数</span><span class="sxs-lookup"><span data-stu-id="e20f6-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="e20f6-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e20f6-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e20f6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e20f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e20f6-105">构造 `ReflectionOracle` qubit 标志唯一标记的目标状态。</span><span class="sxs-lookup"><span data-stu-id="e20f6-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="e20f6-106">目标状态的单个 qubit 设置为1，其他所有0： $ \ket {1} _f $。</span><span class="sxs-lookup"><span data-stu-id="e20f6-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="e20f6-107">输入</span><span class="sxs-lookup"><span data-stu-id="e20f6-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="e20f6-108">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e20f6-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e20f6-109">用于标记 qubit $f $ 的 oracle 的索引。</span><span class="sxs-lookup"><span data-stu-id="e20f6-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="e20f6-110">输出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="e20f6-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="e20f6-111">`ReflectionOracle`，它反映 $ \ket _f $ 标记的状态 {1} 。</span><span class="sxs-lookup"><span data-stu-id="e20f6-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="e20f6-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e20f6-112">See Also</span></span>

- [<span data-ttu-id="e20f6-113">Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="e20f6-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)