---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: ea160bb9a0a8bb5106c3e37a6a16155bad71dd25
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856046"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="89342-102">EvolutionUnitary 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="89342-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="89342-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="89342-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="89342-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89342-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89342-105">表示单一的时间演化运算符。</span><span class="sxs-lookup"><span data-stu-id="89342-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="89342-106">第一个参数是时间演化的持续时间，第二个参数是由单一参数操作的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="89342-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

