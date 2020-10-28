---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700405"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="a98cc-102">StatePreparationComplexCoefficients 函数</span><span class="sxs-lookup"><span data-stu-id="a98cc-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="a98cc-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a98cc-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a98cc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a98cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a98cc-105">返回准备特定量程状态的操作。</span><span class="sxs-lookup"><span data-stu-id="a98cc-105">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="a98cc-106">返回的操作 $U $ 准备带有复数系数的任意量程状态 $ \ket{\psi} $ $r 从 $n $-qubit 计算基础状态 $ \ket{0...0} $ _j e ^ {i t_j} $。</span><span class="sxs-lookup"><span data-stu-id="a98cc-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="a98cc-107">新分配的寄存器上的 U 操作由 $ $ \begin{align} U\ket {0 ... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="a98cc-107">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="a98cc-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a98cc-108">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a98cc-109">输入</span><span class="sxs-lookup"><span data-stu-id="a98cc-109">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="a98cc-110">系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="a98cc-110">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="a98cc-111">由最多 $ 2 ^ n $ 个复数系数表示的数组，其绝对值和阶段 $ (r_j，t_j) $。</span><span class="sxs-lookup"><span data-stu-id="a98cc-111">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="a98cc-112">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="a98cc-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="a98cc-113">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a98cc-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a98cc-114">状态准备单一操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="a98cc-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="a98cc-115">注解</span><span class="sxs-lookup"><span data-stu-id="a98cc-115">Remarks</span></span>

<span data-ttu-id="a98cc-116">负的输入系数 $r 将被视为值为 $ | r_j | $ 的 _j < $0。</span><span class="sxs-lookup"><span data-stu-id="a98cc-116">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="a98cc-117">`coefficients` 将用元素 $ (r_j，t_j) = (0.0，0.0) $ （如果指定少于 $ 2 ^ n $）。</span><span class="sxs-lookup"><span data-stu-id="a98cc-117">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>