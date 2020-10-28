---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700781"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="f3345-102">StateOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="f3345-102">StateOracle user defined type</span></span>

<span data-ttu-id="f3345-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="f3345-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="f3345-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3345-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3345-105">表示 oracle for 状态准备。</span><span class="sxs-lookup"><span data-stu-id="f3345-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="f3345-106">Oracle $O $ 的输入为：</span><span class="sxs-lookup"><span data-stu-id="f3345-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="f3345-107">对标志 qubit $f $ 进行索引的整数。</span><span class="sxs-lookup"><span data-stu-id="f3345-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="f3345-108">系统注册 $s $，将存储所需的量程状态 $ \ket{\psi} \_ s $。</span><span class="sxs-lookup"><span data-stu-id="f3345-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="f3345-109">注解</span><span class="sxs-lookup"><span data-stu-id="f3345-109">Remarks</span></span>

<span data-ttu-id="f3345-110">此 oracle 定义者： $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，$ $ 作用于 on 计算基础状态 $ \ket {0} \_ {f} \ket {0} \_ s $，以 \_ 在 $ \ket{\psi} {1} f $ 标志的基础上创建包含波幅 $ \lambda $ 的目标状态 $ \ket s $ \_ 。</span><span class="sxs-lookup"><span data-stu-id="f3345-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="f3345-111">第一个参数是 $ \ket f $ 的 qubit 寄存器的索引 {0} \_ 。</span><span class="sxs-lookup"><span data-stu-id="f3345-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="f3345-112">第二个参数包含两个寄存器。</span><span class="sxs-lookup"><span data-stu-id="f3345-112">The second parameter encompassed both registers.</span></span>