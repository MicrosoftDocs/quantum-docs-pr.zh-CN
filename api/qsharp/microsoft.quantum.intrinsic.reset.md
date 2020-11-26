---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重置操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198667"
---
# <a name="reset-operation"></a><span data-ttu-id="50dc5-102">重置操作</span><span class="sxs-lookup"><span data-stu-id="50dc5-102">Reset operation</span></span>

<span data-ttu-id="50dc5-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="50dc5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="50dc5-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="50dc5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="50dc5-105">给定单个 qubit，对其进行度量，并确保其处于 | 0 ⟩状态，以便可以安全地释放它。</span><span class="sxs-lookup"><span data-stu-id="50dc5-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="50dc5-106">输入</span><span class="sxs-lookup"><span data-stu-id="50dc5-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="50dc5-107">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="50dc5-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="50dc5-108">其状态将重置为 $ \ket $ 的 qubit {0} 。</span><span class="sxs-lookup"><span data-stu-id="50dc5-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50dc5-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50dc5-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

