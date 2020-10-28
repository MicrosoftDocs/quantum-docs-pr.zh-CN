---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695095"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="8e524-102">PrepareUniformSuperposition 操作</span><span class="sxs-lookup"><span data-stu-id="8e524-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="8e524-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8e524-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8e524-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e524-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e524-105">创建对 superposition 进行编码的状态为0的统一 `nIndices - 1` 。</span><span class="sxs-lookup"><span data-stu-id="8e524-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="8e524-106">也就是说，在给定输入状态 $ \ket{0\cdots 0} $ 的情况下，此单一 $U $ 将在所有数字状态 $0 $ 到 $M-$1 上创建一个统一的 superposition。</span><span class="sxs-lookup"><span data-stu-id="8e524-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="8e524-107">换句话说，$ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}。</span><span class="sxs-lookup"><span data-stu-id="8e524-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="8e524-108">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="8e524-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="8e524-109">输入</span><span class="sxs-lookup"><span data-stu-id="8e524-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="8e524-110">nIndices： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e524-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e524-111">统一 superposition 中所需的状态数 $M $。</span><span class="sxs-lookup"><span data-stu-id="8e524-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="8e524-112">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8e524-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8e524-113">以格式存储数字状态的 qubit 寄存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="8e524-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="8e524-114">此注册必须能够将数字存储 $M-$1，并假定在状态 $ \ket{0\cdots 0} $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="8e524-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e524-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e524-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8e524-116">注解</span><span class="sxs-lookup"><span data-stu-id="8e524-116">Remarks</span></span>

<span data-ttu-id="8e524-117">此操作为 adjointable，但 `indexRegister` `nIndices` 在这种情况下，要求在 superposition 的基础上是统一的。</span><span class="sxs-lookup"><span data-stu-id="8e524-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>