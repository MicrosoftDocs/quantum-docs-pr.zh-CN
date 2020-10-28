---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695866"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx 函数

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

软件包 [](https://nuget.org/packages/)


将数据格式的 Hamiltonian 术语的索引转换 `HTerm[]` 为 GeneratorIndex。

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>输入

### <a name="data--hterm"></a>数据： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

输入格式的数据 `HTerm[]` 。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)[]

添加到 GeneratorIndex 的其他信息。


### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

Hamiltonian 术语的索引



## <a name="output--generatorindex"></a>输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

表示由表示的 Hamiltonian 术语的 GeneratorIndex `data[idx]` ，以及添加的附加信息 `termType` 。