---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840045"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。
修饰符 `CA` 指示操作可以控制和 adjointable。

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>输入

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

返回操作的函数。



## <a name="output--tu--unit--is-adj--ctl"></a>输出： ( t，' U) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

扩充函数第一个参数的类型。
### <a name="u"></a>' U

扩充函数的第二个参数的类型。

## <a name="see-also"></a>另请参阅

- [Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)