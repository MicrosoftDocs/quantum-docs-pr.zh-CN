---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 2b8e7fc0e7881d8c1bd6f14c150476262b7a2b19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849319"
---
# <a name="resetall-operation"></a><span data-ttu-id="df213-102">ResetAll 操作</span><span class="sxs-lookup"><span data-stu-id="df213-102">ResetAll operation</span></span>

<span data-ttu-id="df213-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="df213-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="df213-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="df213-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="df213-105">给定一个 qubits 数组，对其进行度量，确保它们处于 | 0 ⟩状态，以便可以安全地释放它们。</span><span class="sxs-lookup"><span data-stu-id="df213-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="df213-106">输入</span><span class="sxs-lookup"><span data-stu-id="df213-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="df213-107">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="df213-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="df213-108">其状态将重置为 $ \ket $ 的 qubits 的数组 {0} 。</span><span class="sxs-lookup"><span data-stu-id="df213-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df213-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df213-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

