---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: eb2dd8750ed5ad9fc75ca24bb4c8ef36298f69f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198769"
---
# <a name="r1frac-operation"></a><span data-ttu-id="550cd-102">R1Frac 操作</span><span class="sxs-lookup"><span data-stu-id="550cd-102">R1Frac operation</span></span>

<span data-ttu-id="550cd-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="550cd-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="550cd-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="550cd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="550cd-105">{1}通过指定为 dyadic 分数的角度，将关于 $ \ket $ 状态的旋转。</span><span class="sxs-lookup"><span data-stu-id="550cd-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="550cd-106">\begin{align} R_1 (n，k) \mathrel{： =} \operatorname{diag} (1，e ^ {i \pi k/2 ^ n} ) 。</span><span class="sxs-lookup"><span data-stu-id="550cd-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="550cd-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="550cd-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="550cd-108">此操作使用 **相反** 的符号约定，不包括中的 @"microsoft.quantum.intrinsic.r" $ 1/2 $ 的因子 @"microsoft.quantum.intrinsic.r1" 。</span><span class="sxs-lookup"><span data-stu-id="550cd-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="550cd-109">输入</span><span class="sxs-lookup"><span data-stu-id="550cd-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="550cd-110">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="550cd-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="550cd-111">Dyadic 中要旋转 qubit 的角度的分数表示形式的分子。</span><span class="sxs-lookup"><span data-stu-id="550cd-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="550cd-112">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="550cd-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="550cd-113">幂 of，指定 qubit 要旋转的角度的分母。</span><span class="sxs-lookup"><span data-stu-id="550cd-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="550cd-114">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="550cd-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="550cd-115">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="550cd-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="550cd-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="550cd-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="550cd-117">备注</span><span class="sxs-lookup"><span data-stu-id="550cd-117">Remarks</span></span>

<span data-ttu-id="550cd-118">等效于：</span><span class="sxs-lookup"><span data-stu-id="550cd-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```