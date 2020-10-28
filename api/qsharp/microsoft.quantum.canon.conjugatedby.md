---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696097"
---
# <a name="conjugatedby-function"></a><span data-ttu-id="9041c-102">ConjugatedBy 函数</span><span class="sxs-lookup"><span data-stu-id="9041c-102">ConjugatedBy function</span></span>

<span data-ttu-id="9041c-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9041c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9041c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9041c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9041c-105">给定的外部和内部操作返回一个新的操作，该操作将由外部操作词干内部操作。</span><span class="sxs-lookup"><span data-stu-id="9041c-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="9041c-106">输入</span><span class="sxs-lookup"><span data-stu-id="9041c-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="9041c-107">outerOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="9041c-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="9041c-108">应使用 $U $ 的操作，该操作应该用于共轭 $V $。</span><span class="sxs-lookup"><span data-stu-id="9041c-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="9041c-109">请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。</span><span class="sxs-lookup"><span data-stu-id="9041c-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="9041c-110">innerOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9041c-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9041c-111">操作 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="9041c-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="9041c-112">输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9041c-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9041c-113">其操作由单一 $U ^ {\dagger} V U $ 表示的新操作。</span><span class="sxs-lookup"><span data-stu-id="9041c-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9041c-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="9041c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9041c-115">找</span><span class="sxs-lookup"><span data-stu-id="9041c-115">'T</span></span>

<span data-ttu-id="9041c-116">每个内部和外部操作作用于的目标的类型。</span><span class="sxs-lookup"><span data-stu-id="9041c-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="9041c-117">注解</span><span class="sxs-lookup"><span data-stu-id="9041c-117">Remarks</span></span>

<span data-ttu-id="9041c-118">外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。</span><span class="sxs-lookup"><span data-stu-id="9041c-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="9041c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9041c-119">See Also</span></span>

- [<span data-ttu-id="9041c-120">Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="9041c-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="9041c-121">Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="9041c-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="9041c-122">Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="9041c-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="9041c-123">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="9041c-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)