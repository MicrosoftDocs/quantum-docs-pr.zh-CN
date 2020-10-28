---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700981"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="6fd95-102">DiscreteOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="6fd95-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="6fd95-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="6fd95-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="6fd95-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fd95-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fd95-105">表示离散 oracle。</span><span class="sxs-lookup"><span data-stu-id="6fd95-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="6fd95-106">这是一种 oracle，它实现 $U ^ m $ $U $ 的固定操作和非负 $m 整数。</span><span class="sxs-lookup"><span data-stu-id="6fd95-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

