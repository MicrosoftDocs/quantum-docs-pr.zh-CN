---
uid: Microsoft.Quantum.Canon.Bound
title: 绑定函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696130"
---
# <a name="bound-function"></a>绑定函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>输入

### <a name="operations--t--unit-"></a>操作：不 => [Unit](xref:microsoft.quantum.lang-ref.unit) []

要对给定输入执行的一系列操作。



## <a name="output--t--unit"></a>输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 

一项新的操作，它对其输入按顺序执行每个给定的操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组中的每个操作的作用。

## <a name="see-also"></a>另请参阅

- [Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Canon. BoundA](xref:Microsoft.Quantum.Canon.BoundA)
- [Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)