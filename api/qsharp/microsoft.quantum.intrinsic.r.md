---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699804"
---
# <a name="r-operation"></a><span data-ttu-id="ab784-102">R 操作</span><span class="sxs-lookup"><span data-stu-id="ab784-102">R operation</span></span>

<span data-ttu-id="ab784-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ab784-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ab784-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab784-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab784-105">应用围绕给定 Pauli 轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="ab784-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="ab784-106">\begin{align} R_ {\mu} ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_ {\mu}/2}，\end{align}，其中，$ \mu \in \{ i，X，Y，Z \} $。</span><span class="sxs-lookup"><span data-stu-id="ab784-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ab784-107">输入</span><span class="sxs-lookup"><span data-stu-id="ab784-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="ab784-108">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ab784-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ab784-109">Pauli 运算符 ($ \mu $) 指数化形成旋转。</span><span class="sxs-lookup"><span data-stu-id="ab784-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="ab784-110">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab784-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab784-111">Qubit 要旋转的角度。</span><span class="sxs-lookup"><span data-stu-id="ab784-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ab784-112">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ab784-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ab784-113">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="ab784-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab784-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab784-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ab784-115">注解</span><span class="sxs-lookup"><span data-stu-id="ab784-115">Remarks</span></span>

<span data-ttu-id="ab784-116">使用调用时 `pauli = PauliI` ，此操作将应用 *全局阶段* 。</span><span class="sxs-lookup"><span data-stu-id="ab784-116">When called with `pauli = PauliI`, this operation applies a *global phase* .</span></span> <span data-ttu-id="ab784-117">与函子一起使用时，此阶段可能很重要 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="ab784-117">This phase can be significant when used with the `Controlled` functor.</span></span>