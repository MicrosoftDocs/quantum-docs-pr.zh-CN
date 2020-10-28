---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695653"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

软件包 [](https://nuget.org/packages/)


创建一个 `arr` 由 start. 枚举的整数数组。步骤 .。。端面.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>输入

### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)

`Range` `start..step..end` 要转换为数组的值的。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

一个新的整数数组，对应于通过循环访问的值 `range` 。