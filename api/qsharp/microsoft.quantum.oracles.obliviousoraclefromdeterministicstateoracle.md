---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 8f1fe34e38edefba228fb9d01e1712e4c0916970
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226683"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="f34cd-102">ObliviousOracleFromDeterministicStateOracle 函数</span><span class="sxs-lookup"><span data-stu-id="f34cd-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="f34cd-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="f34cd-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="f34cd-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f34cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f34cd-105">将 oracles 和组合在一起 `DeterministicStateOracle` `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f34cd-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="f34cd-106">输入</span><span class="sxs-lookup"><span data-stu-id="f34cd-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="f34cd-107">ancillaOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="f34cd-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="f34cd-108">一种状态，它准备 $a $ 的注册，oracle $A $ 的类型 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f34cd-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="f34cd-109">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="f34cd-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="f34cd-110">类型为的 oracle $U $ `ObliviousOracle` ，它在注册 $a，s $ 上合作。</span><span class="sxs-lookup"><span data-stu-id="f34cd-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="f34cd-111">输出： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="f34cd-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="f34cd-112">Oracle $O = UA $ of 类型 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f34cd-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f34cd-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f34cd-113">See Also</span></span>

- [<span data-ttu-id="f34cd-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="f34cd-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="f34cd-115">Oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="f34cd-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)