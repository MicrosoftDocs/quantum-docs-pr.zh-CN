---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842576"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="efa6d-102">DiscreteOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="efa6d-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="efa6d-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="efa6d-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="efa6d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="efa6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="efa6d-105">表示离散 oracle。</span><span class="sxs-lookup"><span data-stu-id="efa6d-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="efa6d-106">这是一种 oracle，它实现 $U ^ m $ $U $ 的固定操作和非负 $m 整数。</span><span class="sxs-lookup"><span data-stu-id="efa6d-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

