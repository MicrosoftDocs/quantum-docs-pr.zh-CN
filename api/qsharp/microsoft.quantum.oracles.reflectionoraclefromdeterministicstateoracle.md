---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700197"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="fd7a5-102">ReflectionOracleFromDeterministicStateOracle 函数</span><span class="sxs-lookup"><span data-stu-id="fd7a5-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="fd7a5-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="fd7a5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="fd7a5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd7a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd7a5-105">从 oracle 构造有关给定状态的反射。</span><span class="sxs-lookup"><span data-stu-id="fd7a5-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="fd7a5-106">说明</span><span class="sxs-lookup"><span data-stu-id="fd7a5-106">Description</span></span>

<span data-ttu-id="fd7a5-107">由于单一矩阵 $O $ 指定了 oracle 确定性状态准备，因此此函数的结果是一个 oracle，它围绕 oracle $O $ 准备的状态 $ \ket{\psi} $ 应用反射。也就是说，状态 $ \ket{\psi} $，以便 $O \ket {0} = \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="fd7a5-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="fd7a5-108">输入</span><span class="sxs-lookup"><span data-stu-id="fd7a5-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="fd7a5-109">oracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="fd7a5-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="fd7a5-110">准备状态 $ \ket{\psi} $ 的副本的 oracle。</span><span class="sxs-lookup"><span data-stu-id="fd7a5-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="fd7a5-111">输出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="fd7a5-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="fd7a5-112">反映状态 $ \ket{\psi} $ 的 oracle。</span><span class="sxs-lookup"><span data-stu-id="fd7a5-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd7a5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd7a5-113">See Also</span></span>

- [<span data-ttu-id="fd7a5-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="fd7a5-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="fd7a5-115">Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="fd7a5-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)