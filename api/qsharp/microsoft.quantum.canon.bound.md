---
uid: Microsoft.Quantum.Canon.Bound
title: 绑定函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841056"
---
# <a name="bound-function"></a>绑定函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

以下项是等效的：

```qsharp
let bound = Bound([U, V]);
bound(x);
```

和

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>另请参阅

- [Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Canon. BoundA](xref:Microsoft.Quantum.Canon.BoundA)
- [Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)