---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695374"
---
# <a name="resetall-operation"></a><span data-ttu-id="b88ab-102">ResetAll 操作</span><span class="sxs-lookup"><span data-stu-id="b88ab-102">ResetAll operation</span></span>

<span data-ttu-id="b88ab-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b88ab-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b88ab-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b88ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b88ab-105">给定一个 qubits 数组，对其进行度量，确保它们处于 | 0 ⟩状态，以便可以安全地释放它们。</span><span class="sxs-lookup"><span data-stu-id="b88ab-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b88ab-106">输入</span><span class="sxs-lookup"><span data-stu-id="b88ab-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="b88ab-107">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b88ab-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b88ab-108">其状态将重置为 $ \ket $ 的 qubits 的数组 {0} 。</span><span class="sxs-lookup"><span data-stu-id="b88ab-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b88ab-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b88ab-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

