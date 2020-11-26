---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191102"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="e6cdb-102">TargetStateReflectionOracle 函数</span><span class="sxs-lookup"><span data-stu-id="e6cdb-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="e6cdb-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e6cdb-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e6cdb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6cdb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6cdb-105">构造 `ReflectionOracle` qubit 标志唯一标记的目标状态。</span><span class="sxs-lookup"><span data-stu-id="e6cdb-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="e6cdb-106">目标状态的单个 qubit 设置为1，其他所有0： $ \ket {1} _f $。</span><span class="sxs-lookup"><span data-stu-id="e6cdb-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="e6cdb-107">输入</span><span class="sxs-lookup"><span data-stu-id="e6cdb-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="e6cdb-108">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e6cdb-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e6cdb-109">用于标记 qubit $f $ 的 oracle 的索引。</span><span class="sxs-lookup"><span data-stu-id="e6cdb-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="e6cdb-110">输出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="e6cdb-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="e6cdb-111">`ReflectionOracle`，它反映 $ \ket _f $ 标记的状态 {1} 。</span><span class="sxs-lookup"><span data-stu-id="e6cdb-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6cdb-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6cdb-112">See Also</span></span>

- [<span data-ttu-id="e6cdb-113">Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="e6cdb-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)