---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850103"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


创建一个 `arr` 由 start. 枚举的整数数组。步骤 .。。端面.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>输入

### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)

`Range` `start..step..end` 要转换为数组的值的。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

一个新的整数数组，对应于通过循环访问的值 `range` 。

## <a name="example"></a>示例

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```