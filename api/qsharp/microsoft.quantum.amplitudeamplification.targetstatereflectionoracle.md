---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700068"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="b394d-102">TargetStateReflectionOracle 函数</span><span class="sxs-lookup"><span data-stu-id="b394d-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="b394d-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b394d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b394d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b394d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b394d-105">构造 `ReflectionOracle` qubit 标志唯一标记的目标状态。</span><span class="sxs-lookup"><span data-stu-id="b394d-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="b394d-106">目标状态的单个 qubit 设置为1，其他所有0： $ \ket {1} _f $。</span><span class="sxs-lookup"><span data-stu-id="b394d-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="b394d-107">输入</span><span class="sxs-lookup"><span data-stu-id="b394d-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="b394d-108">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b394d-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b394d-109">用于标记 qubit $f $ 的 oracle 的索引。</span><span class="sxs-lookup"><span data-stu-id="b394d-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="b394d-110">输出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b394d-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b394d-111">`ReflectionOracle`，它反映 $ \ket _f $ 标记的状态 {1} 。</span><span class="sxs-lookup"><span data-stu-id="b394d-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="b394d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b394d-112">See Also</span></span>

- [<span data-ttu-id="b394d-113">Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="b394d-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)