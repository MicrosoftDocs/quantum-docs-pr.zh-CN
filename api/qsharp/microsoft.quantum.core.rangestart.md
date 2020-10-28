---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695625"
---
# <a name="rangestart-function"></a>RangeStart 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

软件包 [](https://nuget.org/packages/)


返回给定范围中定义的开始值。

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>输入

### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

给定范围的定义起始值。

## <a name="remarks"></a>注解

范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。

请注意，定义的范围的起始值与序列的第一个元素相同，除非该范围指定一个空序列 (例如 2.。 1）。