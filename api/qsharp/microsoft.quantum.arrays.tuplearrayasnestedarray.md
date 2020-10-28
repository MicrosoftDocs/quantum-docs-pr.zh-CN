---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696445"
---
# <a name="tuplearrayasnestedarray-function"></a>TupleArrayAsNestedArray 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


将2元组的列表转换为嵌套数组。

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a>输入

### <a name="tuplelist--tt"></a>tupleList： ( t，不) []

要转换为嵌套数组的2元组的列表。



## <a name="output--t"></a>输出： t [] []

长度与 tupleList 匹配的嵌套数组。

## <a name="example"></a>示例

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

