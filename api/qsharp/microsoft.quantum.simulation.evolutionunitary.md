---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700961"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="30c18-102">EvolutionUnitary 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="30c18-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="30c18-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="30c18-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="30c18-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="30c18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="30c18-105">表示单一的时间演化运算符。</span><span class="sxs-lookup"><span data-stu-id="30c18-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="30c18-106">第一个参数是时间演化的持续时间，第二个参数是由单一参数操作的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="30c18-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

