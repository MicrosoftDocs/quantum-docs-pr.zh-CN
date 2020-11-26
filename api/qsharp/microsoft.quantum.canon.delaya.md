---
uid: Microsoft.Quantum.Canon.DelayA
title: DelayA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207133"
---
# <a name="delaya-operation"></a>DelayA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用给定操作，延迟。

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a>描述

给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。
具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。
表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。

## <a name="input"></a>输入

### <a name="op--t--unit--is-adj"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

要应用的操作。


### <a name="arg--t"></a>arg： t

将操作应用到的输入。


### <a name="aux--unit"></a>aux： [Unit](xref:microsoft.quantum.lang-ref.unit)

用于通过使用部分应用程序延迟操作应用程序的参数。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要延迟的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delay)
- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delayed)