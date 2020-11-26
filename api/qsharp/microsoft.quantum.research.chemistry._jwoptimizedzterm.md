---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: _JWOptimizedZTerm 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: 7c2ab2e7bbe628748dd4b6c022c4c96ad37ac314
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225816"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="3b2f0-102">_JWOptimizedZTerm 操作</span><span class="sxs-lookup"><span data-stu-id="3b2f0-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="3b2f0-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3b2f0-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="3b2f0-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3b2f0-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="3b2f0-105">按描述的 Z 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="3b2f0-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3b2f0-106">输入</span><span class="sxs-lookup"><span data-stu-id="3b2f0-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3b2f0-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3b2f0-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3b2f0-108">`GeneratorIndex` 表示 Z 术语的。</span><span class="sxs-lookup"><span data-stu-id="3b2f0-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3b2f0-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b2f0-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b2f0-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="3b2f0-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="3b2f0-111">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3b2f0-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3b2f0-112">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="3b2f0-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3b2f0-113">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3b2f0-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3b2f0-114">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="3b2f0-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b2f0-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b2f0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

