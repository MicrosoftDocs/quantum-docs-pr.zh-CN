---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843890"
---
# <a name="targetstatereflectionoracle-function"></a>TargetStateReflectionOracle 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


构造 `ReflectionOracle` qubit 标志唯一标记的目标状态。

目标状态的单个 qubit 设置为1，其他所有0： $ \ket {1} _f $。

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>输入

### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

用于标记 qubit $f $ 的 oracle 的索引。



## <a name="output--reflectionoracle"></a>输出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

`ReflectionOracle`，它反映 $ \ket _f $ 标记的状态 {1} 。

## <a name="see-also"></a>另请参阅

- [Canon. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)