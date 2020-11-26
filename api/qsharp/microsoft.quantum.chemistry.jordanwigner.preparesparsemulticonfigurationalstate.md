---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: PrepareSparseMultiConfigurationalState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 4d39be70c48ed49a1eec410ed6f8e5081dc1e8ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224762"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="eb4fb-102">PrepareSparseMultiConfigurationalState 操作</span><span class="sxs-lookup"><span data-stu-id="eb4fb-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="eb4fb-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="eb4fb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="eb4fb-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="eb4fb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="eb4fb-105">通过将 excitations 添加到初始试用状态，对试用状态进行稀疏的多配置状态准备。</span><span class="sxs-lookup"><span data-stu-id="eb4fb-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="eb4fb-106">输入</span><span class="sxs-lookup"><span data-stu-id="eb4fb-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="eb4fb-107">initialStatePreparation： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb4fb-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eb4fb-108">用于准备初始试用状态的单一订阅。</span><span class="sxs-lookup"><span data-stu-id="eb4fb-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="eb4fb-109">excitations： [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="eb4fb-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="eb4fb-110">初始试用状态的 Excitations，由 excitation 和 excitation 操作的 qubit 索引表示。</span><span class="sxs-lookup"><span data-stu-id="eb4fb-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="eb4fb-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb4fb-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb4fb-112">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="eb4fb-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb4fb-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb4fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

