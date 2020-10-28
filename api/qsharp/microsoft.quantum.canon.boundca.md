---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696120"
---
# <a name="boundca-function"></a>BoundCA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。
修饰符 `CA` 指示数组中的所有操作都是 adjointable 且可控制的。

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="operations--t--unit-adj--ctl"></a>操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl []

要对给定输入执行的一系列操作。



## <a name="output--t--unit-adj--ctl"></a>输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

一项新的操作，它对其输入按顺序执行每个给定的操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组中的每个操作的作用。

## <a name="see-also"></a>另请参阅

- [Canon。](xref:Microsoft.Quantum.Canon.Bound)