---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695932"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定一个函数和一个操作，返回一个新的操作，其输入由给定函数转换。

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="fn--u---t"></a>fn： ' U->

将给定输入转换为操作所需的格式的函数。


### <a name="op--t--unit-adj--ctl"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要转换的操作。



## <a name="output--u--unit-adj--ctl"></a>输出： "U => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

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