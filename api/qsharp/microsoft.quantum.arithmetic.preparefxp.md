---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 29ba66700db83d0786a70841c7b03843a9ae6219
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222399"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="bf852-102">PrepareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="bf852-102">PrepareFxP operation</span></span>

<span data-ttu-id="bf852-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bf852-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bf852-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="bf852-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="bf852-105">将量程固定点数字初始化为传统常量。</span><span class="sxs-lookup"><span data-stu-id="bf852-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bf852-106">输入</span><span class="sxs-lookup"><span data-stu-id="bf852-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="bf852-107">常量： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bf852-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bf852-108">要将量程固定点初始化为的常数。</span><span class="sxs-lookup"><span data-stu-id="bf852-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="bf852-109">fp： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="bf852-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="bf852-110">要初始化的 FixedPoint) 类型的固定点数字 (。</span><span class="sxs-lookup"><span data-stu-id="bf852-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf852-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf852-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

