---
uid: Microsoft.Quantum.Arrays.Any
title: 任何函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696556"
---
# <a name="any-function"></a>任何函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定为数组元素定义的数组和谓词，检查数组中是否至少有一个元素满足该谓词。

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>输入

### <a name="predicate--t---bool"></a>谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值

用于 `'T` `Bool` 检查元素的的函数。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`Bool`应用于所有元素的谓词或函数的值。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。

## <a name="remarks"></a>注解

函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个函数， `predicate: 'T -> Bool` 我们就可以生成一个 `Bool` 值，该值指示某个元素是否满足 `predicate` 。