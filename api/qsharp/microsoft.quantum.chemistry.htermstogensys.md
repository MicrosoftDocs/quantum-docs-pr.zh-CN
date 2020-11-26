---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204107"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys 函数

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


将数据格式的 Hamiltonian 转换 `HTerm[]` 为 GeneratorSystem。

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>输入

### <a name="data--hterm"></a>数据： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

输入格式的数据 `HTerm[]` 。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)[]

添加到 GeneratorIndex 的其他信息。



## <a name="output--generatorsystem"></a>输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

表示由输入表示的 Hamiltonian 的 GeneratorSystem `data` 。