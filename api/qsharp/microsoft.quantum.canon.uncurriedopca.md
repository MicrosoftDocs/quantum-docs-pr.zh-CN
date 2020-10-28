---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695916"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定一个返回操作的函数，返回一个将两个输入作为元组的新操作。
修饰符 `CA` 指示操作可以控制和 adjointable。

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>输入

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp：不 > "U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词

返回操作的函数。



## <a name="output--tu--unit-ctl--adj"></a>输出： ( t，' U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词

与 `op` 等效的新操作 `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

扩充函数第一个参数的类型。
### <a name="u"></a>' U

扩充函数的第二个参数的类型。

## <a name="see-also"></a>另请参阅

- [Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)