---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202203"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="fc3f5-102">AssertQubitIsInStateWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="fc3f5-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="fc3f5-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fc3f5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fc3f5-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fc3f5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fc3f5-105">断言处于预期状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="fc3f5-106">`expected` 表示复杂向量，$ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="fc3f5-107">元组的第一个元素表示每个 $a $，$b $ 是复数的实部，第二个元素是复数的实部。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="fc3f5-108">最后一个参数定义进行断言的公差。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="fc3f5-109">输入</span><span class="sxs-lookup"><span data-stu-id="fc3f5-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="fc3f5-110">应为： ([复杂](xref:Microsoft.Quantum.Math.Complex)的[复杂](xref:Microsoft.Quantum.Math.Complex)) </span><span class="sxs-lookup"><span data-stu-id="fc3f5-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="fc3f5-111">需要分别为 $ \ket {0} $ 和 $ \ket $ 的复杂 amplitudes {1} 。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="fc3f5-112">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fc3f5-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fc3f5-113">要断言其状态的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="fc3f5-114">请注意，假定此 qubit 与其他已分配的 qubits 分离，而不是放大。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="fc3f5-115">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc3f5-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc3f5-116">允许实际 amplitudes 偏离预期值的附加容差。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="fc3f5-117">有关详细信息，请参阅下面的备注。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc3f5-118">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc3f5-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fc3f5-119">备注</span><span class="sxs-lookup"><span data-stu-id="fc3f5-119">Remarks</span></span>

<span data-ttu-id="fc3f5-120">以下 Mathematica 代码可用于验证 mi、mx、my、mz 的表达式：</span><span class="sxs-lookup"><span data-stu-id="fc3f5-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="fc3f5-121">容差是 \_ 三维实向量 (x ₂之间的 $L {\infty} $ 距离。 x ₃、x ₄) 由 $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ 和实矢量 (y ₂、y ₃、y ₄定义，) 由复数 = Y ₁ I + y ₂ x + y ₃ y + y ₄ Z 定义，其中复数是与寄存器状态相对应的密度矩阵。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="fc3f5-122">这在假设 Tr (复数) 和 Tr (| ψ⟩⟨ψ |) 都是 1 (例如 x ₁ = 1/2、y ₁ = 1/2) 。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="fc3f5-123">如果不是这种情况，则该函数将断言 (x ₂-x ₁，x ₃-x ₁，x ₄-x ₁，x ₄ + x ₁) 和 (y ₂-y ₁，y ₃ + y ₁) 小于公差参数的∞距离。</span><span class="sxs-lookup"><span data-stu-id="fc3f5-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>