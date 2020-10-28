---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695624"
---
# <a name="rangestep-function"></a>RangeStep 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

软件包 [](https://nuget.org/packages/)


返回一个整数，该整数指定如何计算范围的下一个值。

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>输入

### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

给定范围的已定义步长值。

## <a name="remarks"></a>注解

范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。