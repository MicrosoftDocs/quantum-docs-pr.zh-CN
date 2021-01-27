---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: c80bb2b394e83c1133ed6ddc1640a3d88563ca6e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818481"
---
# <a name="rfrac-operation"></a><span data-ttu-id="f0c2b-102">RFrac 操作</span><span class="sxs-lookup"><span data-stu-id="f0c2b-102">RFrac operation</span></span>

<span data-ttu-id="f0c2b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f0c2b-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f0c2b-105">通过指定为 dyadic 分数的角度，对给定 Pauli 轴进行旋转。</span><span class="sxs-lookup"><span data-stu-id="f0c2b-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="f0c2b-106">\begin{align} R_ {\mu} (n，k) \mathrel{： =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}，\end{align} 其中，$ \mu \in \{ i，X，Y，Z \} $。</span><span class="sxs-lookup"><span data-stu-id="f0c2b-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="f0c2b-107">此操作使用中的 **相反** 符号约定 @"microsoft.quantum.intrinsic.r" 。</span><span class="sxs-lookup"><span data-stu-id="f0c2b-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f0c2b-108">输入</span><span class="sxs-lookup"><span data-stu-id="f0c2b-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="f0c2b-109">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f0c2b-110">要指数化以形成旋转的 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="f0c2b-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="f0c2b-111">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f0c2b-112">Dyadic 中要旋转 qubit 的角度的分数表示形式的分子。</span><span class="sxs-lookup"><span data-stu-id="f0c2b-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="f0c2b-113">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f0c2b-114">幂 of，指定 qubit 要旋转的角度的分母。</span><span class="sxs-lookup"><span data-stu-id="f0c2b-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="f0c2b-115">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f0c2b-116">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="f0c2b-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0c2b-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f0c2b-118">备注</span><span class="sxs-lookup"><span data-stu-id="f0c2b-118">Remarks</span></span>

<span data-ttu-id="f0c2b-119">等效于：</span><span class="sxs-lookup"><span data-stu-id="f0c2b-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```