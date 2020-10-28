---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 5bbc8d6113fb36bfd4050b98538bb61bbac02185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696679"
---
# <a name="paulicoefficientfromgenidx-function"></a>PauliCoefficientFromGenIdx 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


提取由描述的 Pauli 术语的系数 `GeneratorIndex` 。

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a>输入

### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` 对 Pauli 术语进行编码的类型。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

描述的术语的系数 `GeneratorIndex` 。