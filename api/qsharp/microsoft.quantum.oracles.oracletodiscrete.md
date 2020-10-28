---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700788"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete 函数

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

软件包 [](https://nuget.org/packages/)


给定一个表示 "黑盒" oracle 的操作，将返回一个独立的 oracle，它表示重复多次的 "黑箱" oracle。

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>输入

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要指数化的操作。



## <a name="output--discreteoracle"></a>输出： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

部分应用于 "黑盒" oracle 的操作，该