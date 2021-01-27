---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重置操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818633"
---
# <a name="reset-operation"></a><span data-ttu-id="1f228-102">重置操作</span><span class="sxs-lookup"><span data-stu-id="1f228-102">Reset operation</span></span>

<span data-ttu-id="1f228-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1f228-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1f228-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1f228-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1f228-105">给定单个 qubit，对其进行度量，并确保其处于 | 0 ⟩状态，以便可以安全地释放它。</span><span class="sxs-lookup"><span data-stu-id="1f228-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1f228-106">输入</span><span class="sxs-lookup"><span data-stu-id="1f228-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="1f228-107">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1f228-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1f228-108">其状态将重置为 $ \ket $ 的 qubit {0} 。</span><span class="sxs-lookup"><span data-stu-id="1f228-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f228-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f228-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

