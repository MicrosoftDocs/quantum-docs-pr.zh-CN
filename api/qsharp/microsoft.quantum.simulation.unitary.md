---
uid: Microsoft.Quantum.Simulation.Unitary
title: 单一用户定义类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701097"
---
# <a name="unitary-user-defined-type"></a><span data-ttu-id="ae9fe-102">单一用户定义类型</span><span class="sxs-lookup"><span data-stu-id="ae9fe-102">Unitary user defined type</span></span>

<span data-ttu-id="ae9fe-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ae9fe-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ae9fe-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae9fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae9fe-105">表示单一运算符下的演变。</span><span class="sxs-lookup"><span data-stu-id="ae9fe-105">Represents evolution under a unitary operator.</span></span>

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

