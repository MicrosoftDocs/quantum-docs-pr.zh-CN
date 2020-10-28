---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimized0123Term
title: _JWOptimized0123Term 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimized0123Term
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 7382f3167055bbc2a499fa9490f89a0eb147e3e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695293"
---
# <a name="_jwoptimized0123term-operation"></a><span data-ttu-id="c1828-102">_JWOptimized0123Term 操作</span><span class="sxs-lookup"><span data-stu-id="c1828-102">_JWOptimized0123Term operation</span></span>

<span data-ttu-id="c1828-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c1828-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c1828-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1828-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1828-105">由描述的 PQRS 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="c1828-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimized0123Term (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c1828-106">输入</span><span class="sxs-lookup"><span data-stu-id="c1828-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="c1828-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c1828-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c1828-108">`GeneratorIndex` 表示 PQRS 术语的。</span><span class="sxs-lookup"><span data-stu-id="c1828-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c1828-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1828-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c1828-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c1828-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="c1828-111">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c1828-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c1828-112">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="c1828-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c1828-113">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c1828-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c1828-114">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="c1828-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1828-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1828-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

