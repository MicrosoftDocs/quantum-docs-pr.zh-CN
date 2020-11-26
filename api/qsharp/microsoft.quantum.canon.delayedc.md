---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206999"
---
# <a name="delayedc-function"></a>DelayedC 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回应用给定自变量的给定操作的操作。

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="op--t--unit--is-ctl"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl

应用返回值后应用的操作


### <a name="arg--t"></a>arg： t

将操作应用到的输入 `op` 。



## <a name="output--unit--unit--is-ctl"></a>输出： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl

适用于输入的新操作 `op``arg`

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要延迟的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delayed)
- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delay)