---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700209"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="220f5-102">ObliviousOracleFromDeterministicStateOracle 函数</span><span class="sxs-lookup"><span data-stu-id="220f5-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="220f5-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="220f5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="220f5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="220f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="220f5-105">将 oracles 和组合在一起 `DeterministicStateOracle` `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="220f5-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="220f5-106">输入</span><span class="sxs-lookup"><span data-stu-id="220f5-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="220f5-107">ancillaOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="220f5-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="220f5-108">一种状态，它准备 $a $ 的注册，oracle $A $ 的类型 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="220f5-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="220f5-109">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="220f5-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="220f5-110">类型为的 oracle $U $ `ObliviousOracle` ，它在注册 $a，s $ 上合作。</span><span class="sxs-lookup"><span data-stu-id="220f5-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="220f5-111">输出： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="220f5-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="220f5-112">Oracle $O = UA $ of 类型 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="220f5-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="220f5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="220f5-113">See Also</span></span>

- [<span data-ttu-id="220f5-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="220f5-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="220f5-115">Oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="220f5-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)