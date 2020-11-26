---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: _ApplyJordanWignerZTerm_ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: ad9245b0fd79b4f383d1ef8531537b03d78ae9b8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203988"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="ee1fa-102">_ApplyJordanWignerZTerm_ 操作</span><span class="sxs-lookup"><span data-stu-id="ee1fa-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="ee1fa-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ee1fa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ee1fa-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ee1fa-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ee1fa-105">按描述的 Z 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="ee1fa-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ee1fa-106">输入</span><span class="sxs-lookup"><span data-stu-id="ee1fa-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="ee1fa-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ee1fa-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ee1fa-108">`GeneratorIndex` 表示 Z 术语的。</span><span class="sxs-lookup"><span data-stu-id="ee1fa-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ee1fa-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee1fa-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee1fa-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="ee1fa-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ee1fa-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ee1fa-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ee1fa-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="ee1fa-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee1fa-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee1fa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

