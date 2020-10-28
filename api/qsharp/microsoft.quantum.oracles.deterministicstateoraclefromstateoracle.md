---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700789"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="81a77-102">DeterministicStateOracleFromStateOracle 函数</span><span class="sxs-lookup"><span data-stu-id="81a77-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="81a77-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="81a77-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="81a77-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81a77-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81a77-105">将类型的 oracle 转换 `StateOracle` 为 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="81a77-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="81a77-106">输入</span><span class="sxs-lookup"><span data-stu-id="81a77-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="81a77-107">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="81a77-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="81a77-108">$A $ 的标志 qubit 的索引 `stateOracle` ，该索引显式作用于两个寄存器： $f $ 和 system $s $，例如 $A \ket {0} \_ f\ket {\ psi} \_ s $。</span><span class="sxs-lookup"><span data-stu-id="81a77-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="81a77-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="81a77-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="81a77-110">准备 oracle $A 类型为的状态 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="81a77-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="81a77-111">输出： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="81a77-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="81a77-112">相同状态准备 oracle $A $，但现在为类型 `DeterministicStateOracle` ，因此它在 $a，而不会再显式分离，如 $A \ket{0\psi} \_ {as} $。</span><span class="sxs-lookup"><span data-stu-id="81a77-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="81a77-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81a77-113">See Also</span></span>

- [<span data-ttu-id="81a77-114">Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="81a77-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="81a77-115">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="81a77-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)