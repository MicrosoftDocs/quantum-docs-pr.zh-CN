---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 2abfbb9d51a98d8ede1b0835875a3771ffda0691
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204719"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="6cccb-102">TrotterArbitraryImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="6cccb-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="6cccb-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6cccb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6cccb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6cccb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6cccb-105">偶序 Trotter – Suzuki 集成器的递归实现。</span><span class="sxs-lookup"><span data-stu-id="6cccb-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6cccb-106">输入</span><span class="sxs-lookup"><span data-stu-id="6cccb-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="6cccb-107">顺序： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cccb-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cccb-108">Trotter-Suzuki 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="6cccb-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="6cccb-109">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cccb-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cccb-110">要分解为时间步长的操作数。</span><span class="sxs-lookup"><span data-stu-id="6cccb-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="6cccb-111">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，is =) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="6cccb-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6cccb-112">接受索引输入的操作 (类型 `Int`) 和 (类型) 的时间输入 `Double` 和一个量程寄存器 (类型 `'T`) 用于分解。</span><span class="sxs-lookup"><span data-stu-id="6cccb-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="6cccb-113">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6cccb-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6cccb-114">模拟每个步骤的大小的乘数。</span><span class="sxs-lookup"><span data-stu-id="6cccb-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="6cccb-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="6cccb-115">target : 'T</span></span>

<span data-ttu-id="6cccb-116">操作作用于的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="6cccb-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6cccb-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cccb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6cccb-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="6cccb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6cccb-119">找</span><span class="sxs-lookup"><span data-stu-id="6cccb-119">'T</span></span>

<span data-ttu-id="6cccb-120">每次步骤应执行的操作的类型;通常为 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="6cccb-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>