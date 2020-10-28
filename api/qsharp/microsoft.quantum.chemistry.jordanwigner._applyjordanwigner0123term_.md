---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: _ApplyJordanWigner0123Term_ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 36590b2ee9f6f6c2b5e076f8e334dfe7b0144e5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695861"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="337dd-102">_ApplyJordanWigner0123Term_ 操作</span><span class="sxs-lookup"><span data-stu-id="337dd-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="337dd-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="337dd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="337dd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="337dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="337dd-105">由描述的 PQRS 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="337dd-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="337dd-106">输入</span><span class="sxs-lookup"><span data-stu-id="337dd-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="337dd-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="337dd-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="337dd-108">`GeneratorIndex` 表示 PQRS 术语的。</span><span class="sxs-lookup"><span data-stu-id="337dd-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="337dd-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="337dd-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="337dd-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="337dd-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="337dd-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="337dd-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="337dd-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="337dd-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="337dd-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="337dd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

