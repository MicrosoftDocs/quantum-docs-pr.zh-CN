---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845002"
---
# <a name="applyifca-operation"></a><span data-ttu-id="6a4c3-102">ApplyIfCA 操作</span><span class="sxs-lookup"><span data-stu-id="6a4c3-102">ApplyIfCA operation</span></span>

<span data-ttu-id="6a4c3-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a4c3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a4c3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a4c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a4c3-105">应用在传统上有条件的单一操作。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6a4c3-106">说明</span><span class="sxs-lookup"><span data-stu-id="6a4c3-106">Description</span></span>

<span data-ttu-id="6a4c3-107">给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="6a4c3-108">如果 `false` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="6a4c3-109">后缀 `CA` 指示要应用的操作是单一 (可控和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="6a4c3-110">输入</span><span class="sxs-lookup"><span data-stu-id="6a4c3-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="6a4c3-111">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="6a4c3-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6a4c3-112">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="6a4c3-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6a4c3-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6a4c3-114">用于控制是否应用 op 的布尔值。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="6a4c3-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="6a4c3-115">target : 'T</span></span>

<span data-ttu-id="6a4c3-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a4c3-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a4c3-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a4c3-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="6a4c3-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a4c3-119">找</span><span class="sxs-lookup"><span data-stu-id="6a4c3-119">'T</span></span>

<span data-ttu-id="6a4c3-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="6a4c3-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="6a4c3-121">示例</span><span class="sxs-lookup"><span data-stu-id="6a4c3-121">Example</span></span>

<span data-ttu-id="6a4c3-122">下面的 qubits 将注册为一个计算基础状态，该状态由给定为值数组的传统位字符串表示 `Bool` ：</span><span class="sxs-lookup"><span data-stu-id="6a4c3-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="6a4c3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a4c3-123">See Also</span></span>

- [<span data-ttu-id="6a4c3-124">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="6a4c3-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="6a4c3-125">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="6a4c3-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="6a4c3-126">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="6a4c3-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)