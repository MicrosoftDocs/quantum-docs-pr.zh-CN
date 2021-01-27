---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: a75d46ef0b38fbcef99b7ab22454e1b5a9475b11
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837776"
---
# <a name="jordanwignergeneratorsystem-function"></a>JordanWignerGeneratorSystem 函数

命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


将描述的 Hamiltonian 转换 `JWOptimizedHTerms` 为用 `GeneratorSystem` `GeneratorIndex` 此文件中定义的约定表示的。

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>输入

### <a name="data--jwoptimizedhterms"></a>数据： [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

格式的 Hamiltonian 说明 `JWOptimizedHTerms` 。



## <a name="output--generatorsystem"></a>输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Hamiltonian 的表示形式 `GeneratorSystem` 。