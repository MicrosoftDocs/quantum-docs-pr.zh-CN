---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696489"
---
# <a name="lookupfunction-function"></a>LookupFunction 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定一个数组，返回返回该数组的元素的函数。

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>输入

### <a name="array--t"></a>array： t []

要表示为查找函数的数组。



## <a name="output--int---t"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int) ->

`f`这样的函数 `f(idx) == f[idx]` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

表示为查找函数的数组元素的类型。

## <a name="remarks"></a>注解

此函数主要用于与将 `Int -> 'T` 函数作为其参数的函数和操作进行互操作。 这种情况很常见，例如，在生成器表示库中，函数用于避免需要在内存中记录整个数组。