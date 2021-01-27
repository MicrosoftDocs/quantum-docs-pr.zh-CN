---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855929"
---
# <a name="continuousoracle-user-defined-type"></a>ContinuousOracle 用户定义的类型

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示连续 oracle。

这是一个 oracle，它实现 $U ( \delta t) ： \ket{\psi (t) } \mapsto \ket{\psi ($，其中) $ 是一个固定操作，其中 $ \delta t $ 是一个非负实数。

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

