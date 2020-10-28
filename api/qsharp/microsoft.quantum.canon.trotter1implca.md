---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 250b80729530a5d3054e037d9dd653904a57f6d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695930"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="04fa6-102">Trotter1ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="04fa6-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="04fa6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="04fa6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="04fa6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="04fa6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="04fa6-105">第一顺序 Trotter – Suzuki 集成器的实现。</span><span class="sxs-lookup"><span data-stu-id="04fa6-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="04fa6-106">输入</span><span class="sxs-lookup"><span data-stu-id="04fa6-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="04fa6-107">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04fa6-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04fa6-108">要分解为时间步长的操作数。</span><span class="sxs-lookup"><span data-stu-id="04fa6-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="04fa6-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)、[Double](xref:microsoft.quantum.lang-ref.double)、t) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="04fa6-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="04fa6-110">接受索引输入的操作 (类型 `Int`) 和 (类型) 的时间输入 `Double` 和一个量程寄存器 (类型 `'T`) 用于分解。</span><span class="sxs-lookup"><span data-stu-id="04fa6-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="04fa6-111">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="04fa6-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="04fa6-112">模拟每个步骤的大小的乘数。</span><span class="sxs-lookup"><span data-stu-id="04fa6-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="04fa6-113">目标： t</span><span class="sxs-lookup"><span data-stu-id="04fa6-113">target : 'T</span></span>

<span data-ttu-id="04fa6-114">操作作用于的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="04fa6-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="04fa6-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04fa6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="04fa6-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="04fa6-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="04fa6-117">找</span><span class="sxs-lookup"><span data-stu-id="04fa6-117">'T</span></span>

<span data-ttu-id="04fa6-118">每次步骤应执行的操作的类型;通常为 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="04fa6-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>