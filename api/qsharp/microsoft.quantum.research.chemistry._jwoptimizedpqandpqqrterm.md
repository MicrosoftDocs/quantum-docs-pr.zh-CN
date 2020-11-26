---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 96ea3e4ada66733502af7531c8be99de44596dca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225884"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="29d5d-102">_JWOptimizedPQandPQQRTerm 操作</span><span class="sxs-lookup"><span data-stu-id="29d5d-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="29d5d-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="29d5d-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="29d5d-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="29d5d-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="29d5d-105">由描述的 PQ 或 PQQR 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="29d5d-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="29d5d-106">输入</span><span class="sxs-lookup"><span data-stu-id="29d5d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="29d5d-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="29d5d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="29d5d-108">`GeneratorIndex` 表示 PQ 或 PQQr 术语的。</span><span class="sxs-lookup"><span data-stu-id="29d5d-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="29d5d-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="29d5d-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="29d5d-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="29d5d-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="29d5d-111">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="29d5d-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="29d5d-112">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="29d5d-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="29d5d-113">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="29d5d-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="29d5d-114">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="29d5d-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29d5d-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29d5d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

