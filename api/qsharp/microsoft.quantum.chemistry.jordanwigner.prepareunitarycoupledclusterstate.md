---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareUnitaryCoupledClusterState
title: PrepareUnitaryCoupledClusterState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareUnitaryCoupledClusterState
qsharp.summary: Unitary coupled-cluster state preparation of trial state
ms.openlocfilehash: 4db31e3e79d27f12178dbf121cd04727c2332c62
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695719"
---
# <a name="prepareunitarycoupledclusterstate-operation"></a><span data-ttu-id="c1ce7-102">PrepareUnitaryCoupledClusterState 操作</span><span class="sxs-lookup"><span data-stu-id="c1ce7-102">PrepareUnitaryCoupledClusterState operation</span></span>

<span data-ttu-id="c1ce7-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="c1ce7-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="c1ce7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1ce7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1ce7-105">单一耦合群集状态准备试验状态</span><span class="sxs-lookup"><span data-stu-id="c1ce7-105">Unitary coupled-cluster state preparation of trial state</span></span>

```qsharp
operation PrepareUnitaryCoupledClusterState (initialStatePreparation : (Qubit[] => Unit), clusterOperator : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], trotterStepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c1ce7-106">输入</span><span class="sxs-lookup"><span data-stu-id="c1ce7-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="c1ce7-107">initialStatePreparation： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1ce7-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c1ce7-108">用于准备初始试用状态的单一订阅。</span><span class="sxs-lookup"><span data-stu-id="c1ce7-108">Unitary to prepare initial trial state.</span></span>


### <a name="clusteroperator--jordanwignerinputstate"></a><span data-ttu-id="c1ce7-109">clusterOperator： [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="c1ce7-109">clusterOperator : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>




### <a name="trotterstepsize--double"></a><span data-ttu-id="c1ce7-110">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1ce7-110">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="c1ce7-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c1ce7-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c1ce7-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="c1ce7-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1ce7-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1ce7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

