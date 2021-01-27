---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855846"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="6d214-102">StatePreparationPositiveCoefficients 函数</span><span class="sxs-lookup"><span data-stu-id="6d214-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="6d214-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6d214-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6d214-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d214-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="6d214-105">StatePreparationPositiveCoefficients 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="6d214-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="6d214-106">请改用 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>。</span><span class="sxs-lookup"><span data-stu-id="6d214-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="6d214-107">返回一个准备给定量程状态的操作。</span><span class="sxs-lookup"><span data-stu-id="6d214-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="6d214-108">返回的操作 $U $ 准备任意量程状态 $ \ket{\psi} $，其中正负系数为 $ \ alpha_j \ge $0，$n $-qubit 计算基础状态 $ \ket{0...0} $。</span><span class="sxs-lookup"><span data-stu-id="6d214-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="6d214-109">新分配的寄存器上的 U 操作是由 $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="6d214-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="6d214-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="6d214-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="6d214-111">输入</span><span class="sxs-lookup"><span data-stu-id="6d214-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="6d214-112">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6d214-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6d214-113">最多 $ 2 ^ n $ 系数 $ \ alpha_j $ 的数组。</span><span class="sxs-lookup"><span data-stu-id="6d214-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="6d214-114">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="6d214-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="6d214-115">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="6d214-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6d214-116">状态准备单一操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="6d214-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="6d214-117">示例</span><span class="sxs-lookup"><span data-stu-id="6d214-117">Example</span></span>

<span data-ttu-id="6d214-118">以下代码片段在 qubit 注册中准备好量程状态 $ \ket{\psi} = \ sqrt {1/8} \ 票证 {0} + \ sqrt {7/8} \ 票证 {2} $ `qubitsLE` 。</span><span class="sxs-lookup"><span data-stu-id="6d214-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="6d214-119">备注</span><span class="sxs-lookup"><span data-stu-id="6d214-119">Remarks</span></span>

<span data-ttu-id="6d214-120">负输入系数 $ \ alpha_j < $0 将被视为具有值 $ | \ alpha_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="6d214-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="6d214-121">`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ alpha_j = $0.0 填充。</span><span class="sxs-lookup"><span data-stu-id="6d214-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>