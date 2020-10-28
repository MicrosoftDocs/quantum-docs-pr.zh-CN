---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695710"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="6b397-102">_prepareTrialStateWrapper 操作</span><span class="sxs-lookup"><span data-stu-id="6b397-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="6b397-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="6b397-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="6b397-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b397-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b397-105">通过定义 adjoint，使其与 EstimateFrequencyA 兼容的专用包装 PrepareTrialState。</span><span class="sxs-lookup"><span data-stu-id="6b397-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="6b397-106">EstimateFrequencyA 在面向 QuantumSimulator 时具有内置的模拟功能，从而加快了其执行速度。</span><span class="sxs-lookup"><span data-stu-id="6b397-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6b397-107">输入</span><span class="sxs-lookup"><span data-stu-id="6b397-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="6b397-108">inputState： ([Int](xref:microsoft.quantum.lang-ref.int)，[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[] ) </span><span class="sxs-lookup"><span data-stu-id="6b397-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="6b397-109">运行 PrepareTrialState 所需的 Jordan-Wigner 输入。</span><span class="sxs-lookup"><span data-stu-id="6b397-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6b397-110">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6b397-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6b397-111">Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="6b397-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b397-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b397-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

