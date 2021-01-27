---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839619"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx 函数

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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