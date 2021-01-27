---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842526"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="c5e88-102">ReflectionOracleFromDeterministicStateOracle 函数</span><span class="sxs-lookup"><span data-stu-id="c5e88-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="c5e88-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c5e88-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c5e88-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5e88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5e88-105">从 oracle 构造有关给定状态的反射。</span><span class="sxs-lookup"><span data-stu-id="c5e88-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="c5e88-106">说明</span><span class="sxs-lookup"><span data-stu-id="c5e88-106">Description</span></span>

<span data-ttu-id="c5e88-107">由于单一矩阵 $O $ 指定了 oracle 确定性状态准备，因此此函数的结果是一个 oracle，它围绕 oracle $O $ 准备的状态 $ \ket{\psi} $ 应用反射。也就是说，状态 $ \ket{\psi} $，以便 $O \ket {0} = \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="c5e88-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="c5e88-108">输入</span><span class="sxs-lookup"><span data-stu-id="c5e88-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="c5e88-109">oracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="c5e88-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="c5e88-110">准备状态 $ \ket{\psi} $ 的副本的 oracle。</span><span class="sxs-lookup"><span data-stu-id="c5e88-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="c5e88-111">输出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="c5e88-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="c5e88-112">反映状态 $ \ket{\psi} $ 的 oracle。</span><span class="sxs-lookup"><span data-stu-id="c5e88-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5e88-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5e88-113">See Also</span></span>

- [<span data-ttu-id="c5e88-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="c5e88-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="c5e88-115">Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="c5e88-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)