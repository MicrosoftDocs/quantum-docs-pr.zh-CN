---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700789"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle 函数

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

软件包 [](https://nuget.org/packages/)


将类型的 oracle 转换 `StateOracle` 为 `DeterministicStateOracle` 。

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>输入

### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

$A $ 的标志 qubit 的索引 `stateOracle` ，该索引显式作用于两个寄存器： $f $ 和 system $s $，例如 $A \ket {0} \_ f\ket {\ psi} \_ s $。


### <a name="stateoracle--stateoracle"></a>stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

准备 oracle $A 类型为的状态 `StateOracle` 。



## <a name="output--deterministicstateoracle"></a>输出： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

相同状态准备 oracle $A $，但现在为类型 `DeterministicStateOracle` ，因此它在 $a，而不会再显式分离，如 $A \ket{0\psi} \_ {as} $。

## <a name="see-also"></a>另请参阅

- [Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)