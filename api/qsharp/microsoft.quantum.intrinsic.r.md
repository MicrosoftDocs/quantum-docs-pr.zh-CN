---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199022"
---
# <a name="r-operation"></a><span data-ttu-id="4dd85-102">R 操作</span><span class="sxs-lookup"><span data-stu-id="4dd85-102">R operation</span></span>

<span data-ttu-id="4dd85-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4dd85-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4dd85-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4dd85-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4dd85-105">应用围绕给定 Pauli 轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="4dd85-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="4dd85-106">\begin{align} R_ {\mu} ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_ {\mu}/2}，\end{align}，其中，$ \mu \in \{ i，X，Y，Z \} $。</span><span class="sxs-lookup"><span data-stu-id="4dd85-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4dd85-107">输入</span><span class="sxs-lookup"><span data-stu-id="4dd85-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="4dd85-108">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="4dd85-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4dd85-109">Pauli 运算符 ($ \mu $) 指数化形成旋转。</span><span class="sxs-lookup"><span data-stu-id="4dd85-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="4dd85-110">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4dd85-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4dd85-111">Qubit 要旋转的角度。</span><span class="sxs-lookup"><span data-stu-id="4dd85-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="4dd85-112">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4dd85-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4dd85-113">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="4dd85-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4dd85-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dd85-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4dd85-115">备注</span><span class="sxs-lookup"><span data-stu-id="4dd85-115">Remarks</span></span>

<span data-ttu-id="4dd85-116">使用调用时 `pauli = PauliI` ，此操作将应用 *全局阶段*。</span><span class="sxs-lookup"><span data-stu-id="4dd85-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="4dd85-117">与函子一起使用时，此阶段可能很重要 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="4dd85-117">This phase can be significant when used with the `Controlled` functor.</span></span>