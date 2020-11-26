---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQandPQQRTerm_
title: _ApplyJordanWignerPQandPQQRTerm_ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQandPQQRTerm_
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 8b6d022c70052a91d3cf6d4549db5ed1434d3fc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203971"
---
# <a name="_applyjordanwignerpqandpqqrterm_-operation"></a><span data-ttu-id="9079a-102">_ApplyJordanWignerPQandPQQRTerm_ 操作</span><span class="sxs-lookup"><span data-stu-id="9079a-102">_ApplyJordanWignerPQandPQQRTerm_ operation</span></span>

<span data-ttu-id="9079a-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9079a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9079a-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9079a-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9079a-105">由描述的 PQ 或 PQQR 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="9079a-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQandPQQRTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9079a-106">输入</span><span class="sxs-lookup"><span data-stu-id="9079a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="9079a-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9079a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9079a-108">`GeneratorIndex` 表示 PQ 或 PQQR 术语的。</span><span class="sxs-lookup"><span data-stu-id="9079a-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="9079a-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9079a-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9079a-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="9079a-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="9079a-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9079a-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9079a-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="9079a-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9079a-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9079a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

