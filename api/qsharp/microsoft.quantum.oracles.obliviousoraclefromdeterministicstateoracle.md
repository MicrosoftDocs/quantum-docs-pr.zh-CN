---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700209"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a>ObliviousOracleFromDeterministicStateOracle 函数

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

软件包 [](https://nuget.org/packages/)


将 oracles 和组合在一起 `DeterministicStateOracle` `ObliviousOracle` 。

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a>输入

### <a name="ancillaoracle--deterministicstateoracle"></a>ancillaOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

一种状态，它准备 $a $ 的注册，oracle $A $ 的类型 `DeterministicStateOracle` 。


### <a name="signaloracle--obliviousoracle"></a>signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

类型为的 oracle $U $ `ObliviousOracle` ，它在注册 $a，s $ 上合作。



## <a name="output--obliviousoracle"></a>输出： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oracle $O = UA $ of 类型 `ObliviousOracle` 。

## <a name="see-also"></a>另请参阅

- [Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracles. ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)