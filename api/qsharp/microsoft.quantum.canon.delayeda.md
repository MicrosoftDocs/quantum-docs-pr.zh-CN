---
uid: Microsoft.Quantum.Canon.DelayedA
title: DelayedA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696065"
---
# <a name="delayeda-function"></a>DelayedA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


返回应用给定自变量的给定操作的操作。

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a>输入

### <a name="op--t--unit-adj"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

应用返回值后应用的操作


### <a name="arg--t"></a>arg： t

将操作应用到的输入 `op` 。



## <a name="output--unit--unit-adj"></a>输出： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整

适用于输入的新操作 `op``arg`

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要延迟的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delayed)
- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delay)