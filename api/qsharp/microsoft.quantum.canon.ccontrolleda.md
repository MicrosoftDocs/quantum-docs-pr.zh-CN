---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696113"
---
# <a name="ccontrolleda-function"></a>CControlledA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。 如果为，则不 `false` 执行任何操作。
修饰符 `A` 指示操作为 adjointable。

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>输入

### <a name="op--t--unit-adj"></a>op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

要有条件地应用的操作。



## <a name="output--boolt--unit-adj"></a>Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

如果经典控制位为 true，则为 op 的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)