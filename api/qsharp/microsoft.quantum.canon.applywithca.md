---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696156"
---
# <a name="applywithca-operation"></a><span data-ttu-id="a6709-102">ApplyWithCA 操作</span><span class="sxs-lookup"><span data-stu-id="a6709-102">ApplyWithCA operation</span></span>

<span data-ttu-id="a6709-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a6709-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a6709-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6709-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6709-105">给定两个操作，将一个操作应用到另一个运算。</span><span class="sxs-lookup"><span data-stu-id="a6709-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="a6709-106">说明</span><span class="sxs-lookup"><span data-stu-id="a6709-106">Description</span></span>

<span data-ttu-id="a6709-107">给定两个操作，分别由单一运算符 $U $ 和 $V $，按 $U ^ {\dagger} V U $ 的顺序应用。</span><span class="sxs-lookup"><span data-stu-id="a6709-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="a6709-108">也就是说，此操作实现由 $U $ $V $ conjugated 指定的单一运算符。</span><span class="sxs-lookup"><span data-stu-id="a6709-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="a6709-109">输入</span><span class="sxs-lookup"><span data-stu-id="a6709-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="a6709-110">outerOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="a6709-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a6709-111">应使用 $U $ 的操作，该操作应该用于共轭 $V $。</span><span class="sxs-lookup"><span data-stu-id="a6709-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="a6709-112">请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。</span><span class="sxs-lookup"><span data-stu-id="a6709-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="a6709-113">innerOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a6709-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a6709-114">操作 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="a6709-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="a6709-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="a6709-115">target : 'T</span></span>

<span data-ttu-id="a6709-116">要提供给外部和内部操作的输入。</span><span class="sxs-lookup"><span data-stu-id="a6709-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6709-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6709-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a6709-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="a6709-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a6709-119">找</span><span class="sxs-lookup"><span data-stu-id="a6709-119">'T</span></span>

<span data-ttu-id="a6709-120">每个内部和外部操作作用于的目标。</span><span class="sxs-lookup"><span data-stu-id="a6709-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6709-121">注解</span><span class="sxs-lookup"><span data-stu-id="a6709-121">Remarks</span></span>

<span data-ttu-id="a6709-122">外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。</span><span class="sxs-lookup"><span data-stu-id="a6709-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6709-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6709-123">See Also</span></span>

- [<span data-ttu-id="a6709-124">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="a6709-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="a6709-125">Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="a6709-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="a6709-126">Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="a6709-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)