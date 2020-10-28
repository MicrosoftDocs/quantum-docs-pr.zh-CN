---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696094"
---
# <a name="conjugatedbyca-function"></a>ConjugatedByCA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定的外部和内部操作返回一个新的操作，该操作将由外部操作词干内部操作。

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="outeroperation--t--unit-adj"></a>outerOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

应使用 $U $ 的操作，该操作应该用于共轭 $V $。 请注意，外部操作 $U $ 需要 adjointable，但不需要进行控制。


### <a name="inneroperation--t--unit-adj--ctl"></a>innerOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

操作 $V $ 正在 conjugated。



## <a name="output--t--unit-adj--ctl"></a>输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

其操作由单一 $U ^ {\dagger} V U $ 表示的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个内部和外部操作作用于的目标的类型。

## <a name="remarks"></a>注解

外部操作始终被认为是 adjointable 的，但不需要控制以便使组合操作可控制。

## <a name="see-also"></a>另请参阅

- [Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)