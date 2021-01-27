---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852399"
---
# <a name="noop-operation"></a><span data-ttu-id="3c82c-102">NoOp 操作</span><span class="sxs-lookup"><span data-stu-id="3c82c-102">NoOp operation</span></span>

<span data-ttu-id="3c82c-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c82c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c82c-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3c82c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3c82c-105">对参数执行 (no op) 的标识操作。</span><span class="sxs-lookup"><span data-stu-id="3c82c-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3c82c-106">说明</span><span class="sxs-lookup"><span data-stu-id="3c82c-106">Description</span></span>

<span data-ttu-id="3c82c-107">此操作采用任何类型的值，但不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="3c82c-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="3c82c-108">这在需要输入操作类型时非常有用，但不应采取任何措施。</span><span class="sxs-lookup"><span data-stu-id="3c82c-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="3c82c-109">例如，如果特定错误更正症状指示未发生错误， `NoOp<Qubit[]>` 则可能是正确的恢复过程。</span><span class="sxs-lookup"><span data-stu-id="3c82c-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="3c82c-110">同样，如果某个操作需要状态准备过程作为输入，则 `NoOp<Qubit[]>` 可使用来准备状态 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="3c82c-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="3c82c-111">输入</span><span class="sxs-lookup"><span data-stu-id="3c82c-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="3c82c-112">输入： t</span><span class="sxs-lookup"><span data-stu-id="3c82c-112">input : 'T</span></span>

<span data-ttu-id="3c82c-113">要忽略的值。</span><span class="sxs-lookup"><span data-stu-id="3c82c-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c82c-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c82c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c82c-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="3c82c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c82c-116">找</span><span class="sxs-lookup"><span data-stu-id="3c82c-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3c82c-117">备注</span><span class="sxs-lookup"><span data-stu-id="3c82c-117">Remarks</span></span>

<span data-ttu-id="3c82c-118">几乎在所有情况下，都 `NoOp` 需要显式指定的类型参数。</span><span class="sxs-lookup"><span data-stu-id="3c82c-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="3c82c-119">例如，与 `NoOp<Qubit>` 相同 <xref:microsoft.quantum.intrinsic.i> 。</span><span class="sxs-lookup"><span data-stu-id="3c82c-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c82c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c82c-120">See Also</span></span>

- [<span data-ttu-id="3c82c-121">。 I</span><span class="sxs-lookup"><span data-stu-id="3c82c-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)