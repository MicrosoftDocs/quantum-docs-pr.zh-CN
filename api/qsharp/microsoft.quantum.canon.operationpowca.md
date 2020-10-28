---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695983"
---
# <a name="operationpowca-function"></a>OperationPowCA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


引发幂运算。
修饰符 `A` 指示该操作是可控制的且 adjointable。

也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>输入

### <a name="op--t--unit-ctl--adj"></a>op： t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词

操作 $U $，表示要重复的入口。


### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

重复 $U $ 的次数。



## <a name="output--t--unit-ctl--adj"></a>输出：不 => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词

表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要为其提供支持的操作的类型。

## <a name="see-also"></a>另请参阅

- [Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)