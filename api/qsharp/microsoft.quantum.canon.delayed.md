---
uid: Microsoft.Quantum.Canon.Delayed
title: 延迟函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696066"
---
# <a name="delayed-function"></a>延迟函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


返回应用给定自变量的给定操作的操作。

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>输入

### <a name="op--t--u"></a>op： t => ' U 

要应用的操作。


### <a name="arg--t"></a>arg： t

将操作应用到的输入。



## <a name="output--unit--u"></a>输出： [Unit](xref:microsoft.quantum.lang-ref.unit) => "U 

适用于输入的新操作 `op``arg`

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要延迟的操作的输入类型。
### <a name="u"></a>' U

要延迟的操作的返回类型。

## <a name="see-also"></a>另请参阅

- [Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Canon. DelayedA](xref:Microsoft.Quantum.Canon.DelayedA)
- [Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Canon。延迟](xref:Microsoft.Quantum.Canon.Delay)