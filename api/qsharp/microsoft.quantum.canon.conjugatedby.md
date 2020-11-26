---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: ed5316d4603c31d7db2cd6b0d7e54b56fc750fcb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216721"
---
# <a name="conjugatedby-function"></a>ConjugatedBy 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定的外部和内部操作返回一个新的操作，该操作将由外部操作词干内部操作。

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>输入

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

应使用 $U $ 的操作，该操作应该用于共轭 $V $。 请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。


### <a name="inneroperation--t--unit"></a>innerOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 

操作 $V $ 正在 conjugated。



## <a name="output--t--unit"></a>输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 

其操作由单一 $U ^ {\dagger} V U $ 表示的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个内部和外部操作作用于的目标的类型。

## <a name="remarks"></a>备注

外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。

## <a name="see-also"></a>另请参阅

- [Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)