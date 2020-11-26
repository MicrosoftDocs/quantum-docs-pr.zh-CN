---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: accbd7b88cc2f6522da20ec1959492310ff0e743
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193890"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="54411-102">DiscreteOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="54411-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="54411-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="54411-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="54411-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54411-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54411-105">表示离散 oracle。</span><span class="sxs-lookup"><span data-stu-id="54411-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="54411-106">这是一种 oracle，它实现 $U ^ m $ $U $ 的固定操作和非负 $m 整数。</span><span class="sxs-lookup"><span data-stu-id="54411-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

