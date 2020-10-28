---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696153"
---
# <a name="applywithinputtransformation-operation"></a>ApplyWithInputTransformation 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定接受某些输入的操作，返回与该操作兼容的输出的函数以及该函数的输入将使用函数将输入转换为操作所需的格式。

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a>输入

### <a name="fn--u---t"></a>fn： ' U->

将给定输入转换为操作所需的格式的函数。


### <a name="op--t--unit"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) 

要应用的操作。


### <a name="input--u"></a>输入： U

函数的输入。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U



## <a name="see-also"></a>另请参阅

- [Canon. ApplyWithInputTransformationA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Canon. ApplyWithInputTransformationCA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)