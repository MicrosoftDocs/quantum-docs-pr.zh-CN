---
uid: Microsoft.Quantum.Canon.ApplyWith
title: ApplyWith 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: fd46f84e30e72672967b90d92f507d2a5c438dba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217299"
---
# <a name="applywith-operation"></a><span data-ttu-id="cdd5e-102">ApplyWith 操作</span><span class="sxs-lookup"><span data-stu-id="cdd5e-102">ApplyWith operation</span></span>

<span data-ttu-id="cdd5e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cdd5e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cdd5e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cdd5e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cdd5e-105">给定两个操作，将一个操作应用到另一个运算。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="cdd5e-106">描述</span><span class="sxs-lookup"><span data-stu-id="cdd5e-106">Description</span></span>

<span data-ttu-id="cdd5e-107">给定两个操作，分别由单一运算符 $U $ 和 $V $，按 $U ^ {\dagger} V U $ 的顺序应用。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="cdd5e-108">也就是说，此操作实现由 $U $ $V $ conjugated 指定的单一运算符。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="cdd5e-109">输入</span><span class="sxs-lookup"><span data-stu-id="cdd5e-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="cdd5e-110">outerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="cdd5e-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cdd5e-111">应使用 $U $ 的操作，该操作应该用于共轭 $V $。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="cdd5e-112">请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="cdd5e-113">innerOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdd5e-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cdd5e-114">操作 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="cdd5e-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="cdd5e-115">target : 'T</span></span>

<span data-ttu-id="cdd5e-116">要提供给外部和内部操作的输入。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdd5e-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdd5e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cdd5e-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="cdd5e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cdd5e-119">找</span><span class="sxs-lookup"><span data-stu-id="cdd5e-119">'T</span></span>

<span data-ttu-id="cdd5e-120">每个内部和外部操作作用于的目标。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdd5e-121">备注</span><span class="sxs-lookup"><span data-stu-id="cdd5e-121">Remarks</span></span>

<span data-ttu-id="cdd5e-122">外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。</span><span class="sxs-lookup"><span data-stu-id="cdd5e-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdd5e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdd5e-123">See Also</span></span>

- [<span data-ttu-id="cdd5e-124">Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="cdd5e-124">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="cdd5e-125">Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="cdd5e-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="cdd5e-126">Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="cdd5e-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)