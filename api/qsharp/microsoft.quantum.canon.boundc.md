---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207575"
---
# <a name="boundc-function"></a>BoundC 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。
修饰符 `C` 指示数组中的所有操作都可控制。

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="operations--t--unit--is-ctl"></a>操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl []

要对给定输入执行的一系列操作。



## <a name="output--t--unit--is-ctl"></a>输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl

一项新的操作，它对其输入按顺序执行每个给定的操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组中的每个操作的作用。

## <a name="see-also"></a>另请参阅

- [Canon。](xref:Microsoft.Quantum.Canon.Bound)