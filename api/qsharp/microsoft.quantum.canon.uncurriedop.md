---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852008"
---
# <a name="uncurriedop-function"></a>UncurriedOp 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>输入

### <a name="curriedop--t---u--unit"></a>curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit) 

返回操作的函数。



## <a name="output--tu--unit"></a>输出： ( t，' U) => [单位](xref:microsoft.quantum.lang-ref.unit) 

与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

扩充操作的第一个输入的类型。
### <a name="u"></a>' U

扩充操作的第二个输入的类型。

## <a name="see-also"></a>另请参阅

- [Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)