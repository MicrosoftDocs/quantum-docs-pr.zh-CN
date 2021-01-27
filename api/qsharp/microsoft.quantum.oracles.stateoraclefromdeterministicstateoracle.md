---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842505"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="ca6bc-102">StateOracleFromDeterministicStateOracle 函数</span><span class="sxs-lookup"><span data-stu-id="ca6bc-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="ca6bc-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ca6bc-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ca6bc-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca6bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca6bc-105">将类型的 oracle 转换 `DeterministicStateOracle` 为 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="ca6bc-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="ca6bc-106">输入</span><span class="sxs-lookup"><span data-stu-id="ca6bc-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="ca6bc-107">deterministicStateOracle： [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="ca6bc-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="ca6bc-108">准备 oracle $A 类型为的状态 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="ca6bc-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="ca6bc-109">输出： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="ca6bc-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="ca6bc-110">相同状态准备 oracle $A $，但现在为类型 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="ca6bc-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="ca6bc-111">请注意，在这种情况下，标志索引 `StateOracle` 是一个虚拟变量，因此不起作用。</span><span class="sxs-lookup"><span data-stu-id="ca6bc-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca6bc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca6bc-112">See Also</span></span>

- [<span data-ttu-id="ca6bc-113">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="ca6bc-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="ca6bc-114">Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="ca6bc-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)