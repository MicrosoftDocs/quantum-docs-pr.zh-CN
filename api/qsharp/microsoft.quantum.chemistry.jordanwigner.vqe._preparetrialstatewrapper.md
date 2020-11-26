---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: 8e1a39cbd307a467ab7f0466c90722e1c8c46d4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224677"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="54580-102">_prepareTrialStateWrapper 操作</span><span class="sxs-lookup"><span data-stu-id="54580-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="54580-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="54580-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="54580-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="54580-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="54580-105">通过定义 adjoint，使其与 EstimateFrequencyA 兼容的专用包装 PrepareTrialState。</span><span class="sxs-lookup"><span data-stu-id="54580-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="54580-106">EstimateFrequencyA 在面向 QuantumSimulator 时具有内置的模拟功能，从而加快了其执行速度。</span><span class="sxs-lookup"><span data-stu-id="54580-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="54580-107">输入</span><span class="sxs-lookup"><span data-stu-id="54580-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="54580-108">inputState： ([Int](xref:microsoft.quantum.lang-ref.int)，[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[] ) </span><span class="sxs-lookup"><span data-stu-id="54580-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="54580-109">运行 PrepareTrialState 所需的 Jordan-Wigner 输入。</span><span class="sxs-lookup"><span data-stu-id="54580-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="54580-110">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="54580-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="54580-111">Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="54580-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54580-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54580-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

