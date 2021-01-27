---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 141c42d335add85103e16598264f781f32ab80fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840854"
---
# <a name="conjugatedbya-function"></a>ConjugatedByA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定的外部和内部操作返回一个新的操作，该操作将由外部操作词干内部操作。

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a>输入

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

应使用 $U $ 的操作，该操作应该用于共轭 $V $。 请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。


### <a name="inneroperation--t--unit--is-adj"></a>innerOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

操作 $V $ 正在 conjugated。



## <a name="output--t--unit--is-adj"></a>输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

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