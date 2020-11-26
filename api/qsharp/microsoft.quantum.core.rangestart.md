---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223997"
---
# <a name="rangestart-function"></a>RangeStart 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回给定范围中定义的开始值。

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>输入

### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

给定范围的定义起始值。

## <a name="remarks"></a>备注

范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。

请注意，定义的范围的起始值与序列的第一个元素相同，除非该范围指定一个空序列 (例如 2.。 1）。