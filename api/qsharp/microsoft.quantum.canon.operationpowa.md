---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 67491c3302392e9793677727606df1baaf4f205a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852356"
---
# <a name="operationpowa-function"></a>OperationPowA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


引发幂运算。
修饰符 `A` 指示操作为 adjointable。

也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>输入

### <a name="op--t--unit--is-adj"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

操作 $U $，表示要重复的入口。


### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

重复 $U $ 的次数。



## <a name="output--t--unit--is-adj"></a>输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要为其提供支持的操作的类型。

## <a name="see-also"></a>另请参阅

- [Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)