---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852378"
---
# <a name="operationpow-function"></a>OperationPow 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


引发幂运算。

也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>输入

### <a name="op--t--unit"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) 

操作 $U $，表示要重复的入口。


### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

重复 $U $ 的次数。



## <a name="output--t--unit"></a>输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 

表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要为其提供支持的操作的类型。

## <a name="see-also"></a>另请参阅

- [Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)