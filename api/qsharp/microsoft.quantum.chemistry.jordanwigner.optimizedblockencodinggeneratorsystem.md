---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: 4320f111fe7a367bce0f79b04b37639090ddb838
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837123"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a>OptimizedBlockEncodingGeneratorSystem 函数

命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


将描述的 Hamiltonian 转换 `JWOptimizedHTerms` 为 `GeneratorSystem` Pauli 的表示形式 `GeneratorIndex` 。

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a>输入

### <a name="data--jwoptimizedhterms"></a>数据： [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

格式的 Hamiltonian 说明 `JWOptimizedHTerms` 。



## <a name="output--optimizedbegeneratorsystem"></a>输出： [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)

Hamiltonian 的表示形式 `GeneratorSystem` 。