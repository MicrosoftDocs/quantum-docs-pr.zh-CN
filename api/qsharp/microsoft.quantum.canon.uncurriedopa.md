---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695918"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。
修饰符 `A` 指示操作是 adjointable 的。

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>输入

### <a name="curriedop--t---u--unit-adj"></a>curriedOp：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

返回操作的函数。



## <a name="output--tu--unit-adj"></a>输出： ( t，' U) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

扩充函数第一个参数的类型。
### <a name="u"></a>' U

扩充函数的第二个参数的类型。

## <a name="see-also"></a>另请参阅

- [Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)