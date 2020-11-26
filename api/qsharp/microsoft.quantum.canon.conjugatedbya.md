---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: eaa104039b857f0469ddc0aaba97698eca20860d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207337"
---
# <a name="conjugatedbya-function"></a><span data-ttu-id="c6d16-102">ConjugatedByA 函数</span><span class="sxs-lookup"><span data-stu-id="c6d16-102">ConjugatedByA function</span></span>

<span data-ttu-id="c6d16-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6d16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6d16-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6d16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6d16-105">给定的外部和内部操作返回一个新的操作，该操作将由外部操作词干内部操作。</span><span class="sxs-lookup"><span data-stu-id="c6d16-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="c6d16-106">输入</span><span class="sxs-lookup"><span data-stu-id="c6d16-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="c6d16-107">outerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="c6d16-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c6d16-108">应使用 $U $ 的操作，该操作应该用于共轭 $V $。</span><span class="sxs-lookup"><span data-stu-id="c6d16-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="c6d16-109">请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。</span><span class="sxs-lookup"><span data-stu-id="c6d16-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="c6d16-110">innerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="c6d16-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c6d16-111">操作 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="c6d16-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="c6d16-112">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="c6d16-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c6d16-113">其操作由单一 $U ^ {\dagger} V U $ 表示的新操作。</span><span class="sxs-lookup"><span data-stu-id="c6d16-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c6d16-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="c6d16-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c6d16-115">找</span><span class="sxs-lookup"><span data-stu-id="c6d16-115">'T</span></span>

<span data-ttu-id="c6d16-116">每个内部和外部操作作用于的目标的类型。</span><span class="sxs-lookup"><span data-stu-id="c6d16-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6d16-117">备注</span><span class="sxs-lookup"><span data-stu-id="c6d16-117">Remarks</span></span>

<span data-ttu-id="c6d16-118">外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。</span><span class="sxs-lookup"><span data-stu-id="c6d16-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6d16-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6d16-119">See Also</span></span>

- [<span data-ttu-id="c6d16-120">Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="c6d16-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="c6d16-121">Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="c6d16-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="c6d16-122">Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="c6d16-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="c6d16-123">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="c6d16-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)