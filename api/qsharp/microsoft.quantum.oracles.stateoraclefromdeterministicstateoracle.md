---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700780"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle 函数

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

软件包 [](https://nuget.org/packages/)


将类型的 oracle 转换 `DeterministicStateOracle` 为 `StateOracle` 。

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>输入

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle： [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

准备 oracle $A 类型为的状态 `DeterministicStateOracle` 。



## <a name="output--stateoracle"></a>输出： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

相同状态准备 oracle $A $，但现在为类型 `StateOracle` 。 请注意，在这种情况下，标志索引 `StateOracle` 是一个虚拟变量，因此不起作用。

## <a name="see-also"></a>另请参阅

- [Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)