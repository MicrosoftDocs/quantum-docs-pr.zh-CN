---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695995"
---
# <a name="noop-operation"></a><span data-ttu-id="790b6-102">NoOp 操作</span><span class="sxs-lookup"><span data-stu-id="790b6-102">NoOp operation</span></span>

<span data-ttu-id="790b6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="790b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="790b6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="790b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="790b6-105">对参数执行 (no op) 的标识操作。</span><span class="sxs-lookup"><span data-stu-id="790b6-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="790b6-106">说明</span><span class="sxs-lookup"><span data-stu-id="790b6-106">Description</span></span>

<span data-ttu-id="790b6-107">此操作采用任何类型的值，但不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="790b6-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="790b6-108">这在需要输入操作类型时非常有用，但不应采取任何措施。</span><span class="sxs-lookup"><span data-stu-id="790b6-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="790b6-109">例如，如果特定错误更正症状指示未发生错误， `NoOp<Qubit[]>` 则可能是正确的恢复过程。</span><span class="sxs-lookup"><span data-stu-id="790b6-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="790b6-110">同样，如果某个操作需要状态准备过程作为输入，则 `NoOp<Qubit[]>` 可使用来准备状态 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="790b6-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="790b6-111">输入</span><span class="sxs-lookup"><span data-stu-id="790b6-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="790b6-112">输入： t</span><span class="sxs-lookup"><span data-stu-id="790b6-112">input : 'T</span></span>

<span data-ttu-id="790b6-113">要忽略的值。</span><span class="sxs-lookup"><span data-stu-id="790b6-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="790b6-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="790b6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="790b6-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="790b6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="790b6-116">找</span><span class="sxs-lookup"><span data-stu-id="790b6-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="790b6-117">注解</span><span class="sxs-lookup"><span data-stu-id="790b6-117">Remarks</span></span>

<span data-ttu-id="790b6-118">几乎在所有情况下，都 `NoOp` 需要显式指定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="790b6-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="790b6-119">例如，与 `NoOp<Qubit>` 相同 <xref:microsoft.quantum.intrinsic.i> 。</span><span class="sxs-lookup"><span data-stu-id="790b6-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="790b6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="790b6-120">See Also</span></span>

- [<span data-ttu-id="790b6-121">。 I</span><span class="sxs-lookup"><span data-stu-id="790b6-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)