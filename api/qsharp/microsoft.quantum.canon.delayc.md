---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: acb817c3322063353dc08c5d6f8c539391b3bf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696071"
---
# <a name="delayc-operation"></a>DelayC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


应用给定操作，延迟。

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>说明

给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。
具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。
表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。

## <a name="input"></a>输入

### <a name="op--t--unit-ctl"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

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