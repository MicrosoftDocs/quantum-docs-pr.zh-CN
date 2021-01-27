---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854554"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="3e468-102">DeterministicStateOracleFromStateOracle 函数</span><span class="sxs-lookup"><span data-stu-id="3e468-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="3e468-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="3e468-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="3e468-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e468-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e468-105">将类型的 oracle 转换 `StateOracle` 为 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="3e468-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="3e468-106">输入</span><span class="sxs-lookup"><span data-stu-id="3e468-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="3e468-107">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e468-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e468-108">$A $ 的标志 qubit 的索引 `stateOracle` ，该索引显式作用于两个寄存器： $f $ 和 system $s $，例如 $A \ket {0} \_ f\ket {\ psi} \_ s $。</span><span class="sxs-lookup"><span data-stu-id="3e468-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="3e468-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="3e468-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="3e468-110">准备 oracle $A 类型为的状态 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="3e468-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="3e468-111">输出： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="3e468-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="3e468-112">相同状态准备 oracle $A $，但现在为类型 `DeterministicStateOracle` ，因此它在 $a，而不会再显式分离，如 $A \ket{0\psi} \_ {as} $。</span><span class="sxs-lookup"><span data-stu-id="3e468-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e468-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e468-113">See Also</span></span>

- [<span data-ttu-id="3e468-114">Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="3e468-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="3e468-115">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="3e468-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)