---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: _ApplyJordanWignerClusterOperatorPQTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: d72ddea439c45936caefa74add4a0444afe4318e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695860"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="1b18d-102">_ApplyJordanWignerClusterOperatorPQTerm 操作</span><span class="sxs-lookup"><span data-stu-id="1b18d-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="1b18d-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1b18d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1b18d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b18d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b18d-105">由描述的群集 operator PQ 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="1b18d-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1b18d-106">输入</span><span class="sxs-lookup"><span data-stu-id="1b18d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="1b18d-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1b18d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1b18d-108">`GeneratorIndex` 表示群集运算符 PQ 术语的。</span><span class="sxs-lookup"><span data-stu-id="1b18d-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="1b18d-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1b18d-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1b18d-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="1b18d-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1b18d-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1b18d-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1b18d-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="1b18d-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b18d-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b18d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

