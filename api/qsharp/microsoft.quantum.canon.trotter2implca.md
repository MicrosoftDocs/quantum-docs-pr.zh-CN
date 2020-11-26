---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 0e3a7e53a4d415e6b5af81d9bb3f52cddf36c4b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204736"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="9a93d-102">Trotter2ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="9a93d-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="9a93d-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a93d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a93d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a93d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a93d-105">第二顺序 Trotter – Suzuki 集成器的实现。</span><span class="sxs-lookup"><span data-stu-id="9a93d-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9a93d-106">输入</span><span class="sxs-lookup"><span data-stu-id="9a93d-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="9a93d-107">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a93d-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a93d-108">要分解为时间步长的操作数。</span><span class="sxs-lookup"><span data-stu-id="9a93d-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="9a93d-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，is =) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9a93d-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9a93d-110">接受索引输入的操作 (类型 `Int`) 和 (类型) 的时间输入 `Double` 和一个量程寄存器 (类型 `'T`) 用于分解。</span><span class="sxs-lookup"><span data-stu-id="9a93d-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="9a93d-111">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9a93d-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9a93d-112">模拟每个步骤的大小的乘数。</span><span class="sxs-lookup"><span data-stu-id="9a93d-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="9a93d-113">目标： t</span><span class="sxs-lookup"><span data-stu-id="9a93d-113">target : 'T</span></span>

<span data-ttu-id="9a93d-114">操作作用于的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="9a93d-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a93d-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a93d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a93d-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="9a93d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a93d-117">找</span><span class="sxs-lookup"><span data-stu-id="9a93d-117">'T</span></span>

<span data-ttu-id="9a93d-118">每次步骤应执行的操作的类型;通常为 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="9a93d-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>