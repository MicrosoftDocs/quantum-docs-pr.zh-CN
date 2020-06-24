---
title: '使用 Microsoft Q # 数字库'
description: 了解有关 Microsoft 量程数字库中可用的类型和操作的信息。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274458"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="16de9-103">使用数字库</span><span class="sxs-lookup"><span data-stu-id="16de9-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="16de9-104">概述</span><span class="sxs-lookup"><span data-stu-id="16de9-104">Overview</span></span>

<span data-ttu-id="16de9-105">数字库包括三个组件</span><span class="sxs-lookup"><span data-stu-id="16de9-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="16de9-106">带有整数添加器和比较运算符的**基本整数算法**</span><span class="sxs-lookup"><span data-stu-id="16de9-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="16de9-107">基于基本功能构建的**高级整数功能**;它包括乘法、除法、反转等。 对于有符号和无符号整数。</span><span class="sxs-lookup"><span data-stu-id="16de9-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="16de9-108">固定点**算术功能**，具有定点初始化、加法、乘法、倒数、多项式计算和度量。</span><span class="sxs-lookup"><span data-stu-id="16de9-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="16de9-109">所有这些组件均可使用单个语句进行访问 `open` ：</span><span class="sxs-lookup"><span data-stu-id="16de9-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="16de9-110">类型</span><span class="sxs-lookup"><span data-stu-id="16de9-110">Types</span></span>

<span data-ttu-id="16de9-111">数字库支持以下类型</span><span class="sxs-lookup"><span data-stu-id="16de9-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="16de9-112">**`LittleEndian`**：表示整数的 qubit 数组 `qArr : Qubit[]` ，其中 `qArr[0]` 表示最小有效位。</span><span class="sxs-lookup"><span data-stu-id="16de9-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="16de9-113">**`SignedLittleEndian`**：与相同 `LittleEndian` ，只不过它表示以两个补码形式存储的带符号整数。</span><span class="sxs-lookup"><span data-stu-id="16de9-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="16de9-114">**`FixedPoint`**：表示包含 qubit 数组的实数 `qArr2 : Qubit[]` 和一个二进制点位置 `pos` ，该位置计算二进制点左侧的二进制位数。</span><span class="sxs-lookup"><span data-stu-id="16de9-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="16de9-115">`qArr2`的存储方式与相同 `SignedLittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="16de9-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="16de9-116">Operations</span><span class="sxs-lookup"><span data-stu-id="16de9-116">Operations</span></span>

<span data-ttu-id="16de9-117">上述三种类型的操作都可用：</span><span class="sxs-lookup"><span data-stu-id="16de9-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="16de9-118">加法</span><span class="sxs-lookup"><span data-stu-id="16de9-118">Addition</span></span>
    - <span data-ttu-id="16de9-119">比较</span><span class="sxs-lookup"><span data-stu-id="16de9-119">Comparison</span></span>
    - <span data-ttu-id="16de9-120">乘法</span><span class="sxs-lookup"><span data-stu-id="16de9-120">Multiplication</span></span>
    - <span data-ttu-id="16de9-121">平方</span><span class="sxs-lookup"><span data-stu-id="16de9-121">Squaring</span></span>
    - <span data-ttu-id="16de9-122">相除（含余数）</span><span class="sxs-lookup"><span data-stu-id="16de9-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="16de9-123">加法</span><span class="sxs-lookup"><span data-stu-id="16de9-123">Addition</span></span>
    - <span data-ttu-id="16de9-124">比较</span><span class="sxs-lookup"><span data-stu-id="16de9-124">Comparison</span></span>
    - <span data-ttu-id="16de9-125">反转模2的补码</span><span class="sxs-lookup"><span data-stu-id="16de9-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="16de9-126">乘法</span><span class="sxs-lookup"><span data-stu-id="16de9-126">Multiplication</span></span>
    - <span data-ttu-id="16de9-127">平方</span><span class="sxs-lookup"><span data-stu-id="16de9-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="16de9-128">准备/初始化到传统值</span><span class="sxs-lookup"><span data-stu-id="16de9-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="16de9-129">加法（古典常量或其他量子固定点）</span><span class="sxs-lookup"><span data-stu-id="16de9-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="16de9-130">比较</span><span class="sxs-lookup"><span data-stu-id="16de9-130">Comparison</span></span>
    - <span data-ttu-id="16de9-131">乘法</span><span class="sxs-lookup"><span data-stu-id="16de9-131">Multiplication</span></span>
    - <span data-ttu-id="16de9-132">平方</span><span class="sxs-lookup"><span data-stu-id="16de9-132">Squaring</span></span>
    - <span data-ttu-id="16de9-133">对偶函数和奇数函数进行了特殊化计算</span><span class="sxs-lookup"><span data-stu-id="16de9-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="16de9-134">互惠（1/x）</span><span class="sxs-lookup"><span data-stu-id="16de9-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="16de9-135">度量值（古典双精度值）</span><span class="sxs-lookup"><span data-stu-id="16de9-135">Measurement (classical Double)</span></span>

<span data-ttu-id="16de9-136">有关这些操作的详细信息和详细信息，请参阅 Q # 库参考文档，网址为[docs.microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="16de9-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="16de9-137">示例：整数加法</span><span class="sxs-lookup"><span data-stu-id="16de9-137">Sample: Integer addition</span></span>

<span data-ttu-id="16de9-138">作为一个基本示例，请考虑操作 $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是说，使用 n-qubit 整数 $x $，n 或（n + 1）-qubit register $y $ 作为输入，后者映射到 sum $ （x + y） $。</span><span class="sxs-lookup"><span data-stu-id="16de9-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="16de9-139">请注意，如果 $y $ 存储在 $n $ 位寄存器中，则 sum 计算为 "2 ^ n $"。</span><span class="sxs-lookup"><span data-stu-id="16de9-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="16de9-140">使用量程开发工具包，可以按如下所示应用此操作：</span><span class="sxs-lookup"><span data-stu-id="16de9-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="16de9-141">示例：计算平滑函数</span><span class="sxs-lookup"><span data-stu-id="16de9-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="16de9-142">若要在量程计算机上评估平滑功能，如 $ \sin （x） $，其中 $x $ 是一个量程 `FixedPoint` 号，量子开发工具包数字库将提供操作 `EvaluatePolynomialFxP` 和 `Evaluate[Even/Odd]PolynomialFxP` 。</span><span class="sxs-lookup"><span data-stu-id="16de9-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="16de9-143">第一种是， `EvaluatePolynomialFxP` 用于计算 $ $ P （x） = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ 其中 $d $ 表示*度*的多项式。</span><span class="sxs-lookup"><span data-stu-id="16de9-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="16de9-144">为此，所需的全部都是多项式系数 `[a_0,..., a_d]` （类型为 `Double[]` ）、输入 `x : FixedPoint` 和输出 `y : FixedPoint` （最初为零）：</span><span class="sxs-lookup"><span data-stu-id="16de9-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="16de9-145">结果（$P （x） = 1 + 2x $）将存储在中 `yFxP` 。</span><span class="sxs-lookup"><span data-stu-id="16de9-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="16de9-146">第二个、 `EvaluateEvenPolynomialFxP` 和第三个 `EvaluateOddPolynomialFxP` 分别是偶函数和奇数函数的专用化。</span><span class="sxs-lookup"><span data-stu-id="16de9-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="16de9-147">也就是说，对于偶数/奇数函数 $f （x） $ 和 $ $ P_ {偶数} （x） = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d}，$ $ $f （x） $ 近似 $P _ {偶} （x） $ 或 $P _ {奇} （x）： = x\cdot P_ {偶} （x） $。</span><span class="sxs-lookup"><span data-stu-id="16de9-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="16de9-148">在 Q # 中，可以按如下所示处理这两种情况：</span><span class="sxs-lookup"><span data-stu-id="16de9-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="16de9-149">计算 $P _ {偶数} （x） = 1 + 2x ^ 2 $，和</span><span class="sxs-lookup"><span data-stu-id="16de9-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="16de9-150">这会计算 $P _ {奇数} （x） = x + 2x ^ 3 $。</span><span class="sxs-lookup"><span data-stu-id="16de9-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="16de9-151">更多示例</span><span class="sxs-lookup"><span data-stu-id="16de9-151">More samples</span></span>

<span data-ttu-id="16de9-152">可以在[主示例存储库](https://github.com/Microsoft/Quantum)中找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="16de9-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="16de9-153">若要开始，请克隆存储库并打开 `Numerics` 子文件夹：</span><span class="sxs-lookup"><span data-stu-id="16de9-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="16de9-154">然后， `cd` 加入其中一个示例文件夹，并通过</span><span class="sxs-lookup"><span data-stu-id="16de9-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
