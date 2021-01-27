---
uid: Microsoft.Quantum.Canon.Delay
title: 延迟操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840653"
---
# <a name="delay-operation"></a>延迟操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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