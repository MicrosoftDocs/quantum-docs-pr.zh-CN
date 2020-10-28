---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695863"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx 函数

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

软件包 [](https://nuget.org/packages/)


将数据格式的 Hamiltonian 术语转换 `HTerm` 为 GeneratorIndex。

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>输入

### <a name="term--hterm"></a>术语： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

输入格式的数据 `HTerm` 。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)[]

添加到 GeneratorIndex 的其他信息。



## <a name="output--generatorindex"></a>输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

表示由表示的 Hamiltonian 术语的 GeneratorIndex `term` ，以及添加的附加信息 `termType` 。