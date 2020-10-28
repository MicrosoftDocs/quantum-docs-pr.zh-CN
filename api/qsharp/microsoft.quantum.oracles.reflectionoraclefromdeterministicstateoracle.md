---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700197"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle 函数

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

软件包 [](https://nuget.org/packages/)


从 oracle 构造有关给定状态的反射。

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>说明

由于单一矩阵 $O $ 指定了 oracle 确定性状态准备，因此此函数的结果是一个 oracle，它围绕 oracle $O $ 准备的状态 $ \ket{\psi} $ 应用反射。也就是说，状态 $ \ket{\psi} $，以便 $O \ket {0} = \ket{\psi} $。

## <a name="input"></a>输入

### <a name="oracle--deterministicstateoracle"></a>oracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

准备状态 $ \ket{\psi} $ 的副本的 oracle。



## <a name="output--reflectionoracle"></a>输出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

反映状态 $ \ket{\psi} $ 的 oracle。

## <a name="see-also"></a>另请参阅

- [Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)