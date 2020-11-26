---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220002"
---
# <a name="unique-function"></a>Unique 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个没有相等相邻元素的新数组。

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>描述

如果给定了某个元素数组和一个用于测试相等性的函数，则此函数将返回一个新数组，其中保留了元素的相对顺序，但所有相等的相邻元素仅筛选为一个元素。

## <a name="input"></a>输入

### <a name="equal--tt---bool"></a>等于： ( 不，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值

比较两个元素的函数，如果为，则此函数将 `a` 视为等于 `b` `equal(a, b)` `true` 。


### <a name="array--t"></a>array： t []

要针对唯一元素进行筛选的数组。



## <a name="output--t"></a>输出： t []

不具有相等相邻元素的数组。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `array` 。

## <a name="remarks"></a>备注

如果有多个元素相等但并不相邻，则输出数组中将出现多个匹配项。  将此函数与结合使用 `Sorted` ，以获取包含整体唯一元素的数组。