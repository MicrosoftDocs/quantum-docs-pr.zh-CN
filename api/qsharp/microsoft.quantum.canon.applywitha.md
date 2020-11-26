---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: ApplyWithA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: b8847d4b3ddb88031ef360f183b86f6483706cc6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207864"
---
# <a name="applywitha-operation"></a>ApplyWithA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定两个操作，将一个操作应用到另一个运算。

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit is Adj
```


## <a name="description"></a>描述

给定两个操作，分别由单一运算符 $U $ 和 $V $，按 $U ^ {\dagger} V U $ 的顺序应用。 也就是说，此操作实现由 $U $ $V $ conjugated 指定的单一运算符。

## <a name="input"></a>输入

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

应使用 $U $ 的操作，该操作应该用于共轭 $V $。 请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。


### <a name="inneroperation--t--unit--is-adj"></a>innerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

操作 $V $ 正在 conjugated。


### <a name="target--t"></a>目标： t

要提供给外部和内部操作的输入。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个内部和外部操作作用于的目标。

## <a name="remarks"></a>备注

外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)