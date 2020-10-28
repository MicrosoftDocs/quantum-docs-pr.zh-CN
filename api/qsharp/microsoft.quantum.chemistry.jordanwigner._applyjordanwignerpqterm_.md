---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: _ApplyJordanWignerPQTerm_ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 8a9b41e17bcc46c5aff2b18455e1eac25620fe35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695855"
---
# <a name="_applyjordanwignerpqterm_-operation"></a><span data-ttu-id="95578-102">_ApplyJordanWignerPQTerm_ 操作</span><span class="sxs-lookup"><span data-stu-id="95578-102">_ApplyJordanWignerPQTerm_ operation</span></span>

<span data-ttu-id="95578-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="95578-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="95578-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95578-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95578-105">由描述的 PQ 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="95578-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="95578-106">输入</span><span class="sxs-lookup"><span data-stu-id="95578-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="95578-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="95578-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="95578-108">`GeneratorIndex` 表示 PQ 术语的。</span><span class="sxs-lookup"><span data-stu-id="95578-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="95578-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="95578-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="95578-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="95578-110">Duration of time-evolution.</span></span>


### <a name="extraparityqubits--qubit"></a><span data-ttu-id="95578-111">extraParityQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="95578-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="95578-112">可选的奇偶校验 qubits，用于翻转时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="95578-112">Optional parity qubits that flip the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="95578-113">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="95578-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="95578-114">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="95578-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95578-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95578-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

