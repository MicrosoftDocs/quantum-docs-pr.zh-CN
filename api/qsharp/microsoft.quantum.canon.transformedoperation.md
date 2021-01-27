---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852057"
---
# <a name="transformedoperation-function"></a>TransformedOperation 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定一个函数和一个操作，返回一个新的操作，其输入由给定函数转换。

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a>输入

### <a name="fn--u---t"></a>fn： ' U->

将给定输入转换为操作所需的格式的函数。


### <a name="op--t--unit"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) 

要转换的操作。



## <a name="output--u--unit"></a>输出： "U => [单位](xref:microsoft.quantum.lang-ref.unit) 

新操作 tbat 的 `fn` 输入调用，然后将结果输出传递给 `op` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U



## <a name="example"></a>示例

以下调用使用 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 将为输入设计的操作转换 @"Microsoft.Quantum.Arithmetic.BigEndian" 为接受类型为的输入的操作 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>另请参阅

- [Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Canon。](xref:Microsoft.Quantum.Canon.Composed)