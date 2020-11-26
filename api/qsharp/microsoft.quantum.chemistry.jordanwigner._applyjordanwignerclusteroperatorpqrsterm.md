---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQRSTerm
title: _ApplyJordanWignerClusterOperatorPQRSTerm 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQRSTerm
qsharp.summary: Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 5e43f81714128629a63befccb31092adbe9c9e82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204039"
---
# <a name="_applyjordanwignerclusteroperatorpqrsterm-operation"></a><span data-ttu-id="2656e-102">_ApplyJordanWignerClusterOperatorPQRSTerm 操作</span><span class="sxs-lookup"><span data-stu-id="2656e-102">_ApplyJordanWignerClusterOperatorPQRSTerm operation</span></span>

<span data-ttu-id="2656e-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2656e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2656e-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2656e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2656e-105">由描述的群集 operator PQRS 术语应用时间演变 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="2656e-105">Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQRSTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2656e-106">输入</span><span class="sxs-lookup"><span data-stu-id="2656e-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="2656e-107">术语： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2656e-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2656e-108">`GeneratorIndex` 表示群集运算符 PQRS 术语的。</span><span class="sxs-lookup"><span data-stu-id="2656e-108">`GeneratorIndex` representing a cluster operator PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="2656e-109">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2656e-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2656e-110">时间推移的持续时间。</span><span class="sxs-lookup"><span data-stu-id="2656e-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2656e-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2656e-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2656e-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="2656e-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2656e-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2656e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

