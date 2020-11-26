---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193924"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="ef284-102">DeterministicStateOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="ef284-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="ef284-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ef284-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ef284-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef284-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef284-105">表示 oracle for 确定性状态准备。</span><span class="sxs-lookup"><span data-stu-id="ef284-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="ef284-106">Oracle $O $ 的输入为：</span><span class="sxs-lookup"><span data-stu-id="ef284-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="ef284-107">将存储所需的量程状态 $ \ket{\psi} \_ s $ 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="ef284-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="ef284-108">备注</span><span class="sxs-lookup"><span data-stu-id="ef284-108">Remarks</span></span>

<span data-ttu-id="ef284-109">此 oracle 定义的 $O \ket {0} = \ket{\psi} $ 对计算基础状态 $ \ket $ 采取操作 {0} ，以创建状态 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="ef284-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="ef284-110">第一个参数是 $ \ket{\psi} $ 的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="ef284-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>