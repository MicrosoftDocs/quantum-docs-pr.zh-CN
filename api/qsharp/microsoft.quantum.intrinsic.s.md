---
uid: Microsoft.Quantum.Intrinsic.S
title: S 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: c697408c4efe1963787b5aee8f0d3bb6b9e64dd5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198446"
---
# <a name="s-operation"></a><span data-ttu-id="3f137-102">S 操作</span><span class="sxs-lookup"><span data-stu-id="3f137-102">S operation</span></span>

<span data-ttu-id="3f137-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3f137-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3f137-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3f137-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3f137-105">将 S 入口应用于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="3f137-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3f137-106">描述</span><span class="sxs-lookup"><span data-stu-id="3f137-106">Description</span></span>

<span data-ttu-id="3f137-107">此操作可由单一 matrix matrix \begin{align} S \mathrel{： =} \begin{bmatrix} 1 & 0 0 的模拟， \\ \\ & i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="3f137-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="3f137-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3f137-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="3f137-109">输入</span><span class="sxs-lookup"><span data-stu-id="3f137-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="3f137-110">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3f137-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3f137-111">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="3f137-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f137-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f137-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

