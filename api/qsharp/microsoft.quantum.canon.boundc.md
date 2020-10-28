---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696125"
---
# <a name="boundc-function"></a>BoundC 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。
修饰符 `C` 指示数组中的所有操作都可控制。

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="operations--t--unit-ctl"></a>操作：不 => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl []

要对给定输入执行的一系列操作。



## <a name="output--t--unit-ctl"></a>输出：不 => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

一项新的操作，它对其输入按顺序执行每个给定的操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组中的每个操作的作用。

## <a name="see-also"></a>另请参阅

- [Canon。](xref:Microsoft.Quantum.Canon.Bound)