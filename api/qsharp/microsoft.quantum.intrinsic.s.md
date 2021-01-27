---
uid: Microsoft.Quantum.Intrinsic.S
title: S 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: be9078dfdcc4eecf317b0542b1c42a8d60466a5f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817531"
---
# <a name="s-operation"></a><span data-ttu-id="fc809-102">S 操作</span><span class="sxs-lookup"><span data-stu-id="fc809-102">S operation</span></span>

<span data-ttu-id="fc809-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fc809-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fc809-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fc809-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fc809-105">将 S 入口应用于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="fc809-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fc809-106">说明</span><span class="sxs-lookup"><span data-stu-id="fc809-106">Description</span></span>

<span data-ttu-id="fc809-107">此操作可由单一 matrix matrix \begin{align} S \mathrel{： =} \begin{bmatrix} 1 & 0 0 的模拟， \\ \\ & i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="fc809-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="fc809-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fc809-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="fc809-109">输入</span><span class="sxs-lookup"><span data-stu-id="fc809-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="fc809-110">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fc809-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fc809-111">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="fc809-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc809-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc809-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

