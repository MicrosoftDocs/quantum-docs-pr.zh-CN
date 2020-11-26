---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: aa5f09f2e1fde878b523b4efc20b86c26ac738ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216534"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="edb08-102">DecomposedIntoTimeStepsCA 函数</span><span class="sxs-lookup"><span data-stu-id="edb08-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="edb08-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="edb08-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="edb08-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edb08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edb08-105">返回为给定操作实现 Trotter – Suzuki 集成器的操作。</span><span class="sxs-lookup"><span data-stu-id="edb08-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="edb08-106">输入</span><span class="sxs-lookup"><span data-stu-id="edb08-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="edb08-107">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edb08-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edb08-108">要分解为时间步长的操作数。</span><span class="sxs-lookup"><span data-stu-id="edb08-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="edb08-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，is =) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="edb08-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="edb08-110">接受 (类型的索引输入 `Int`) 和时间输入 (类型 `Double` 为分解的) 的操作。</span><span class="sxs-lookup"><span data-stu-id="edb08-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="edb08-111">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edb08-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edb08-112">选择要使用的 Trotter – Suzuki 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="edb08-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="edb08-113">订单1，甚至订单2，4，6,.。。当前支持。</span><span class="sxs-lookup"><span data-stu-id="edb08-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="edb08-114">输出： ([Double](xref:microsoft.quantum.lang-ref.double)，t) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="edb08-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="edb08-115">返回一个实现 Trotter – Suzuki 集成器的单一参数，其中第一个参数 `Double` 是集成步骤大小，第二个参数是目标。</span><span class="sxs-lookup"><span data-stu-id="edb08-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="edb08-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="edb08-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="edb08-117">找</span><span class="sxs-lookup"><span data-stu-id="edb08-117">'T</span></span>

<span data-ttu-id="edb08-118">每次步骤应执行的操作的类型;通常为 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="edb08-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="edb08-119">备注</span><span class="sxs-lookup"><span data-stu-id="edb08-119">Remarks</span></span>

<span data-ttu-id="edb08-120">当使用 `order` 等于时 `1` ，此函数将返回一个操作，该操作可由最低顺序 Trotter – Suzuki 集成器 $ $ \begin{align} S_1 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}，\end{align} $ $，我们已遵循 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139) 的表示法，并让 $ \lambda $ 成为) 的第一次输入所表示的演化时间 (并让 $ \{ H_j \} _ {j = 1} ^ {m} $ 是要集成的 (Hermitian) dynamical 生成器的集合，这 `op(j, lambda, _)` 是由单一运算符 $e ^ {H_j \lambda} $ 模拟的。</span><span class="sxs-lookup"><span data-stu-id="edb08-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="edb08-121">同样， `order` `2` 返回第二顺序对称 Trotter – Suzuki 集成器 $ $ \begin{align} S_2 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}。</span><span class="sxs-lookup"><span data-stu-id="edb08-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="edb08-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="edb08-122">\end{align} $$</span></span>

<span data-ttu-id="edb08-123">更高的值 `order` 是使用 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139)的递归构造实现的。</span><span class="sxs-lookup"><span data-stu-id="edb08-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="edb08-124">参考</span><span class="sxs-lookup"><span data-stu-id="edb08-124">References</span></span>

- [<span data-ttu-id="edb08-125">*D. Berry，Ahokas，Cleve，Sanders，，*</span><span class="sxs-lookup"><span data-stu-id="edb08-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)