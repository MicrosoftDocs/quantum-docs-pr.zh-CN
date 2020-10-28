---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695985"
---
# <a name="operationpowc-function"></a>OperationPowC 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


引发幂运算。
修饰符 `C` 指示操作可控制。

也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="op--t--unit-ctl"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

操作 $U $，表示要重复的入口。


### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

重复 $U $ 的次数。



## <a name="output--t--unit-ctl"></a>输出：不 => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要为其提供支持的操作的类型。

## <a name="see-also"></a>另请参阅

- [Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)