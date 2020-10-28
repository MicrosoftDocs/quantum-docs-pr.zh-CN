---
uid: Microsoft.Quantum.Canon.Delay
title: 延迟操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696075"
---
# <a name="delay-operation"></a>延迟操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


应用给定操作，延迟。

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>说明

给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。
具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。
表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。

## <a name="input"></a>输入

### <a name="op--t--u"></a>op： t => ' U 

要应用的操作。


### <a name="arg--t"></a>arg： t

将操作应用到的输入。


### <a name="aux--unit"></a>aux： [Unit](xref:microsoft.quantum.lang-ref.unit)

用于通过使用部分应用程序延迟操作应用程序的参数。



## <a name="output--u"></a>输出： U



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要延迟的操作的输入类型。
### <a name="u"></a>' U

要延迟的操作的返回类型。

## <a name="see-also"></a>另请参阅

- [Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Canon. DelayA](xref:Microsoft.Quantum.Canon.DelayA)
- [Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delayed)