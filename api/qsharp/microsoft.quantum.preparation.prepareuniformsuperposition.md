---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854316"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="e1cd0-102">PrepareUniformSuperposition 操作</span><span class="sxs-lookup"><span data-stu-id="e1cd0-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="e1cd0-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e1cd0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e1cd0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1cd0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1cd0-105">创建对 superposition 进行编码的状态为0的统一 `nIndices - 1` 。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="e1cd0-106">也就是说，在给定输入状态 $ \ket{0\cdots 0} $ 的情况下，此单一 $U $ 将在所有数字状态 $0 $ 到 $M-$1 上创建一个统一的 superposition。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="e1cd0-107">换句话说，$ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="e1cd0-108">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e1cd0-109">输入</span><span class="sxs-lookup"><span data-stu-id="e1cd0-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="e1cd0-110">nIndices： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1cd0-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1cd0-111">统一 superposition 中所需的状态数 $M $。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="e1cd0-112">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1cd0-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e1cd0-113">以格式存储数字状态的 qubit 寄存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="e1cd0-114">此注册必须能够将数字存储 $M-$1，并假定在状态 $ \ket{0\cdots 0} $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1cd0-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1cd0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="e1cd0-116">示例</span><span class="sxs-lookup"><span data-stu-id="e1cd0-116">Example</span></span>

<span data-ttu-id="e1cd0-117">下面的示例准备 {1} $3 $ qubits 上的状态 $ \frac {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-117">The following example prepares the state $\frac{1}{\sqrt{6}}\sum_{j=0}^{5}\ket{j}$ on $3$ qubits.</span></span>

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a><span data-ttu-id="e1cd0-118">备注</span><span class="sxs-lookup"><span data-stu-id="e1cd0-118">Remarks</span></span>

<span data-ttu-id="e1cd0-119">此操作为 adjointable，但 `indexRegister` `nIndices` 在这种情况下，要求在 superposition 的基础上是统一的。</span><span class="sxs-lookup"><span data-stu-id="e1cd0-119">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>