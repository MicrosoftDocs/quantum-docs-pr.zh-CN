---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850377"
---
# <a name="applywithinputtransformation-operation"></a>ApplyWithInputTransformation 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>示例

以下调用使用将 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 为输入设计的操作应用于 @"Microsoft.Quantum.Arithmetic.BigEndian" 类型的输入 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a>另请参阅

- [Canon. ApplyWithInputTransformationA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Canon. ApplyWithInputTransformationCA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)