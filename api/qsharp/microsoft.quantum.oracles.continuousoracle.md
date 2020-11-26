---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226785"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="fe6cb-102">ContinuousOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="fe6cb-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="fe6cb-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="fe6cb-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="fe6cb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe6cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe6cb-105">表示连续 oracle。</span><span class="sxs-lookup"><span data-stu-id="fe6cb-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="fe6cb-106">这是一个 oracle，它实现 $U ( \delta t) ： \ket{\psi (t) } \mapsto \ket{\psi ($，其中) $ 是一个固定操作，其中 $ \delta t $ 是一个非负实数。</span><span class="sxs-lookup"><span data-stu-id="fe6cb-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

