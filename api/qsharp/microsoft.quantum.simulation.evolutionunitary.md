---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 38e7da28d4146df9cc132ad69ee939c44bc917f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225255"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="a7f79-102">EvolutionUnitary 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="a7f79-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="a7f79-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a7f79-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a7f79-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7f79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7f79-105">表示单一的时间演化运算符。</span><span class="sxs-lookup"><span data-stu-id="a7f79-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="a7f79-106">第一个参数是时间演化的持续时间，第二个参数是由单一参数操作的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="a7f79-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

