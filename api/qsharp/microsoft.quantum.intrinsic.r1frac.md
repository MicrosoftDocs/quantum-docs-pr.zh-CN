---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699793"
---
# <a name="r1frac-operation"></a><span data-ttu-id="ddf42-102">R1Frac 操作</span><span class="sxs-lookup"><span data-stu-id="ddf42-102">R1Frac operation</span></span>

<span data-ttu-id="ddf42-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ddf42-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ddf42-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ddf42-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ddf42-105">{1}通过指定为 dyadic 分数的角度，将关于 $ \ket $ 状态的旋转。</span><span class="sxs-lookup"><span data-stu-id="ddf42-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="ddf42-106">\begin{align} R_1 (n，k) \mathrel{： =} \operatorname{diag} (1，e ^ {i \pi k/2 ^ n} ) 。</span><span class="sxs-lookup"><span data-stu-id="ddf42-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="ddf42-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ddf42-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="ddf42-108">此操作使用 **相反** 的符号约定，不包括中的 @"microsoft.quantum.intrinsic.r" $ 1/2 $ 的因子 @"microsoft.quantum.intrinsic.r1" 。</span><span class="sxs-lookup"><span data-stu-id="ddf42-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ddf42-109">输入</span><span class="sxs-lookup"><span data-stu-id="ddf42-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="ddf42-110">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddf42-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddf42-111">Dyadic 中要旋转 qubit 的角度的分数表示形式的分子。</span><span class="sxs-lookup"><span data-stu-id="ddf42-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="ddf42-112">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddf42-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddf42-113">幂 of，指定 qubit 要旋转的角度的分母。</span><span class="sxs-lookup"><span data-stu-id="ddf42-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ddf42-114">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ddf42-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ddf42-115">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="ddf42-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ddf42-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddf42-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ddf42-117">注解</span><span class="sxs-lookup"><span data-stu-id="ddf42-117">Remarks</span></span>

<span data-ttu-id="ddf42-118">等效于：</span><span class="sxs-lookup"><span data-stu-id="ddf42-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```