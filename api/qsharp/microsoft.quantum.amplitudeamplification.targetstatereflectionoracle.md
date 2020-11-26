---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191102"
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