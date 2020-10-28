---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: b6867a076b654337f6127657189a8453c9973cc2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695933"
---
# <a name="transformedoperationc-function"></a>TransformedOperationC 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定一个函数和一个操作，返回一个新的操作，其输入由给定函数转换。

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="fn--u---t"></a>fn： ' U->

将给定输入转换为操作所需的格式的函数。


### <a name="op--t--unit-ctl"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

要转换的操作。



## <a name="output--u--unit-ctl"></a>输出： "U => [单位](xref:microsoft.quantum.lang-ref.unit) Ctl

新操作 tbat 的 `fn` 输入调用，然后将结果输出传递给 `op` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U



## <a name="see-also"></a>另请参阅

- [Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Canon。](xref:Microsoft.Quantum.Canon.Composed)