---
uid: Microsoft.Quantum.Intrinsic.S
title: S 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: 8a57c60ac1df8f6e94b58acf7183c47f395d291a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700332"
---
# <a name="s-operation"></a><span data-ttu-id="bee29-102">S 操作</span><span class="sxs-lookup"><span data-stu-id="bee29-102">S operation</span></span>

<span data-ttu-id="bee29-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="bee29-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="bee29-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bee29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bee29-105">将 S 入口应用于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="bee29-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="bee29-106">说明</span><span class="sxs-lookup"><span data-stu-id="bee29-106">Description</span></span>

<span data-ttu-id="bee29-107">此操作可由单一 matrix matrix \begin{align} S \mathrel{： =} \begin{bmatrix} 1 & 0 0 的模拟， \\ \\ & i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="bee29-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="bee29-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="bee29-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="bee29-109">输入</span><span class="sxs-lookup"><span data-stu-id="bee29-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="bee29-110">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bee29-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bee29-111">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="bee29-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bee29-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bee29-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

