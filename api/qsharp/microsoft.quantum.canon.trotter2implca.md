---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852021"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="7f1ff-102">Trotter2ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="7f1ff-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="7f1ff-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7f1ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7f1ff-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f1ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f1ff-105">第二顺序 Trotter – Suzuki 集成器的实现。</span><span class="sxs-lookup"><span data-stu-id="7f1ff-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7f1ff-106">输入</span><span class="sxs-lookup"><span data-stu-id="7f1ff-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="7f1ff-107">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f1ff-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7f1ff-108">要分解为时间步长的操作数。</span><span class="sxs-lookup"><span data-stu-id="7f1ff-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="7f1ff-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，is =) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="7f1ff-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7f1ff-110">接受索引输入的操作 (类型 `Int`) 和 (类型) 的时间输入 `Double` 和一个量程寄存器 (类型 `'T`) 用于分解。</span><span class="sxs-lookup"><span data-stu-id="7f1ff-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="7f1ff-111">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7f1ff-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7f1ff-112">模拟每个步骤的大小的乘数。</span><span class="sxs-lookup"><span data-stu-id="7f1ff-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="7f1ff-113">目标： t</span><span class="sxs-lookup"><span data-stu-id="7f1ff-113">target : 'T</span></span>

<span data-ttu-id="7f1ff-114">操作作用于的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="7f1ff-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f1ff-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f1ff-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7f1ff-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="7f1ff-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7f1ff-117">找</span><span class="sxs-lookup"><span data-stu-id="7f1ff-117">'T</span></span>

<span data-ttu-id="7f1ff-118">每次步骤应执行的操作的类型;通常为 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="7f1ff-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="7f1ff-119">示例</span><span class="sxs-lookup"><span data-stu-id="7f1ff-119">Example</span></span>

<span data-ttu-id="7f1ff-120">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="7f1ff-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

<span data-ttu-id="7f1ff-121">和</span><span class="sxs-lookup"><span data-stu-id="7f1ff-121">and</span></span>

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```