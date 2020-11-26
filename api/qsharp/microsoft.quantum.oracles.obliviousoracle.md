---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 2f92dcb28ec669229dfaf9bcb23eef9234552b8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193873"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="edacb-102">ObliviousOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="edacb-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="edacb-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="edacb-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="edacb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edacb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edacb-105">表示 oracle for 在意波幅放大。</span><span class="sxs-lookup"><span data-stu-id="edacb-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="edacb-106">Oracle $O $ 的输入为：</span><span class="sxs-lookup"><span data-stu-id="edacb-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="edacb-107">Ancilla 注册了 $O $ $a $ 的操作。</span><span class="sxs-lookup"><span data-stu-id="edacb-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="edacb-108">系统注册 $s $，将对其应用所需的单一 $U $，并在 register $a $ $ \ket{t} \_ a $。</span><span class="sxs-lookup"><span data-stu-id="edacb-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="edacb-109">备注</span><span class="sxs-lookup"><span data-stu-id="edacb-109">Remarks</span></span>

<span data-ttu-id="edacb-110">此 oracle 定义者： $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ 作用于 ancilla 状态 $ \ket{s} \_ a $，在任何系统状态 $ \ket{\psi} s $ 上实现单一 $U $，该操作 \_ 由 $ \lambda \_ a $ 标记。</span><span class="sxs-lookup"><span data-stu-id="edacb-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="edacb-111">第一个参数是 $ \ket{s} 的 qubit 寄存器 \_ $。</span><span class="sxs-lookup"><span data-stu-id="edacb-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="edacb-112">第二个参数是 $ \ket{\psi} s $ 的 qubit 寄存器 \_ 。</span><span class="sxs-lookup"><span data-stu-id="edacb-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>