---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 8de1ddf0bf176853b33926be7647bc5d1d35095d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696158"
---
# <a name="applywithc-operation"></a>ApplyWithC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定两个操作，将一个操作应用到另一个运算。

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit
```


## <a name="description"></a>说明

给定两个操作，分别由单一运算符 $U $ 和 $V $，按 $U ^ {\dagger} V U $ 的顺序应用。 也就是说，此操作实现由 $U $ $V $ conjugated 指定的单一运算符。

## <a name="input"></a>输入

### <a name="outeroperation--t--unit-adj"></a>outerOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

应使用 $U $ 的操作，该操作应该用于共轭 $V $。 请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。


### <a name="inneroperation--t--unit-ctl"></a>innerOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

操作 $V $ 正在 conjugated。


### <a name="target--t"></a>目标： t

要提供给外部和内部操作的输入。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个内部和外部操作作用于的目标。

## <a name="remarks"></a>注解

外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。

## <a name="see-also"></a>另请参阅

- [Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)