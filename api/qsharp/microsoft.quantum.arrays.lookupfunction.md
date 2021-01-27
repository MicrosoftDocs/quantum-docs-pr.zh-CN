---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845704"
---
# <a name="lookupfunction-function"></a>LookupFunction 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="remarks"></a>备注

此函数主要用于与将 `Int -> 'T` 函数作为其参数的函数和操作进行互操作。 这种情况很常见，例如，在生成器表示库中，函数用于避免需要在内存中记录整个数组。