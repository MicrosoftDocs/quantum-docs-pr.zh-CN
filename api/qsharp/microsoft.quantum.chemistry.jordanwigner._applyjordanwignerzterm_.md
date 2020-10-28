---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: _ApplyJordanWignerZTerm_ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: f42c2ba7570f32d3f26ff82dd4a0ee6f9677fa30
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695848"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="e75a3-102">_ApplyJordanWignerZTerm_ 操作</span><span class="sxs-lookup"><span data-stu-id="e75a3-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="e75a3-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e75a3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e75a3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e75a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e75a3-105">按描述的 Z 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="e75a3-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e75a3-106">输入</span><span class="sxs-lookup"><span data-stu-id="e75a3-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="e75a3-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e75a3-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e75a3-108">`GeneratorIndex` 表示 Z 术语的。</span><span class="sxs-lookup"><span data-stu-id="e75a3-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="e75a3-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e75a3-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e75a3-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="e75a3-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e75a3-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e75a3-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e75a3-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="e75a3-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e75a3-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e75a3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

