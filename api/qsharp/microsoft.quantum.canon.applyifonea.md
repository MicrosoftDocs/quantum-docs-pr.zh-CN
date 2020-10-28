---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696329"
---
# <a name="applyifonea-operation"></a>ApplyIfOneA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


应用一个 adjointable 操作，该操作可将传统结果值视为1。

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a>说明

给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。 如果 `Zero` 为，则不会发生任何事情 `target` 。
后缀 `A` 指示要应用的操作是 adjointable。

## <a name="input"></a>输入

### <a name="result--__invalidresult__"></a>结果： __无效 <Result>__

用于控制是否应用 op 的测量结果。


### <a name="op--t--unit-adj"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

要有条件地应用的操作。


### <a name="target--t"></a>目标： t

将操作应用到的输入。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)